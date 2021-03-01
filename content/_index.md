---
title: 'Root'
type: page
layout: root
---

# StackMuncher static pages root

This page should only be visible in development. Production file structure:

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
* `hugo --cleanDestinationDir`
* `hugo deploy -v`

## Attribution

* Hugo theme based on https://github.com/zerostaticthemes/hugo-serif-theme
* Illustrations:
  *  https://www.vecteezy.com/vector-art/180398-software-engineers
  *  https://www.vecteezy.com/vector-art/180387-software-engineers-vectors
  *  https://www.vecteezy.com/vector-art/107819-free-social-media-vector-illustration