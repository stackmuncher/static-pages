# StackMuncher Static Site Theme with Content

Production file structure:

```
/ - directory root, list of recently updated profiles
/about* - this statically generated site
/* - directory pages
```

## Deployment

Hugo cannot deploy a site to a subfolder on S3. It is always deployed to the root of the bucket.
Since this site resides in */about/* folder the structure has been set up to imitate the deployed structure with this message in the root
and the rest of the pages in */about/*.

The GWAPI should be configured to send any `/about` and `/about/` requests to S3 for SSG contents and any other requests to the directory Lambda.

`hugo deploy` for S3 does not read the keys from *~/.aws/credentials*. You need to add these 2 env vars to the terminal session:

```
export AWS_ACCESS_KEY_ID=
export AWS_SECRET_ACCESS_KEY=
```

## Shortcuts

* `hugo server -v --disableFastRender`
* `hugo --cleanDestinationDir && hugo deploy -v`

## Attribution

* Hugo theme based on https://github.com/zerostaticthemes/hugo-serif-theme, but not much left of it here, hence it's not a fork.
* Illustrations:
  *  https://www.vecteezy.com/vector-art/180398-software-engineers
  *  https://www.vecteezy.com/vector-art/180387-software-engineers-vectors
  *  https://www.vecteezy.com/vector-art/107819-free-social-media-vector-illustration

## Live stats

There is one tiny script in *call-to-action* partial block that loads the latest stats from a JSON file stored in S3 via CloudFront. The config requires this CORS policy in S3:

```json
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "GET",
            "HEAD"
        ],
        "AllowedOrigins": [
            "*"
        ],
        "ExposeHeaders": [
            "access-control-allow-origin"
        ]
    }
]
```
Set *Origin Request Policy* in CloudFront Behaviors tab to `Managed-CORS-S3Origin` to allow the headers through. 

* https://d14nv0i5oq0azm.cloudfront.net/latest_stats.json has a single record
* https://d14nv0i5oq0azm.cloudfront.net/combined_stats.json has the timeline and may be quite large