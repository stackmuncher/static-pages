---
title: 'How to donate a GitHub token to an Open Source project'
date: "2021-11-17"
categories: [ "how-to" ]
tags: [
    "github",
    "contribute"
]
---

Access to [GitHub API](https://docs.github.com/en/rest) has limits on how many requests GitHub accepts from a given service. Adding tokens donated by GitHub members helps open source projects like [stackmuncher.com](https://stackmuncher.com) process more data faster.
 

 

## Step by step instructions
 

#### 1. Navigate to https://github.com/settings/tokens
It will take you to *Personal access tokens* page. Click on *Generate new token* to open a new token form.

![Personal access tokens menu](/about/images/posts/how-to-donate-github-token/4-gen-new-token-link.png)  
 

 


#### 2. Fill in the token form.
E.g. name it *stackmuncher*, set its expiration and leave all the other checkboxes (scopes) unchecked. This will limit the token to Public GitHub API and ensure that none of your private data can be accessed.

![New token form](/about/images/posts/how-to-donate-github-token/5-new-token-form.png)

Click on *Generate token* at the bottom of the page.
 

 


#### 3. Copy the newly generated token and email it to info@stackmuncher.com

![New token](/about/images/posts/how-to-donate-github-token/6-token-generated.png)

* You can delete the token on that same page when you no longer want it to be used
 

 

## How your token can be used

A token with no additional access rights (no boxes checked on when creating it) can access only public data for all of GitHub. It cannot access any of your or anyone else's private repositories or personal data.

GitHub allows up to [5,000 API requests per member](https://docs.github.com/en/rest/overview/resources-in-the-rest-api#rate-limiting) across all member tokens. We limit our use to 1,000 requests per token to make sure your other GitHub apps are not affected.

If your token expires or you delete it we will get *Access denied* from GitHub and will remove your token from our database .