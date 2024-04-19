# ICER's mkdocs website template

# **WORK IN PROGRESS**

This is a shell of an [mkdocs](http://mkdocs.org) based static website that uses [Material for mkdocs](https://squidfunk.github.io/mkdocs-material/) theme and a few plugins.   It is to be used by [MSU-ICER](https://icer.msu.edu) sub-projects that need a stand-alone website

There goal is to have a starting place to create a basic ICER-branded website managed by staff using mkdocs. This was created based on the ICER docs website https://docs.icer.msu.edu

## Process for setting up a dev environment:

**work in progress!**
 
 *these instructions are not complete and not test yet, and will change as work work out using forks, sub-repos, etc*

This will create a new website project with ICER branding that you can use as a starting point for a new webdsite. 


Requires understanding of Python, git, github, ssh with git, markdown and mkdocs.  MkDocs has excellent documentation.  

1. download a zip of this project.  It's not recommended to clone as you will use it to start a new project.   If you are feeling intrepid you can fork this repo and use branches to keep it up-to-date with the template changes, but no guarantee this will work as intended
1. unzip the project files which will create a new folder
1. rename the folder for your project
1. edit the file mkdocs.yml to reflect your project name. 
1. Add your SSH public keys to your gitlab and github accounts. Forward your keys from your laptop using ssh -A if you're doing this on the HPCC.
1. Get access to our github org so you can create a repository ( Ask admins to get added and create an empty repo for you to hold your new project site)


## Editing with mkdocs

this is a short summary of mkdocs good [getting started documentation](https://www.mkdocs.org/getting-started/#creating-a-new-project)*

In that directory you can do `mkdocs build` or `mkdocs serve`; `mkdocs build` will create static files that you can browse with Firefox/Chrome; `mkdocs serve` will set up a test webserver on the local box that you can access via http://localhost:xxxx that will automatically reload as you edit.  If you'd like to edit on the system,. You can use Firefox within OnDemand's Interactive Desktop if you are running on a HPCC dev node (or set up port forwarding back to your local laptop).


The ICER docs are edited on gitlab for security, and have a gitlab "CI" workflow that automatically pushes up to GitHub Pages. If there's a failure a red X will appear next to the commit on the header; If there's a system failure clicking the retry button will re push it up; if there's a syntax error (?) that might not resolve it.

If your project and this website code does not contain any sensitive information (passwords, API keys, etc) you can use a personal github repo with pages set up (https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site and adding another git remote for your own repo and using the remote_name flag to gh-deploy). You don't need to do `mkdocs gh-deploy` to render and push it to github.

<!-- example work session based on MSU ICER docs repo only, may not apply to your template -->
<!-- 
```
keenandr@DESKTOP-RMC6KCH:~$ git clone git@gitlab.msu.edu:icer/public-documentation.git
Cloning into 'public-documentation'...
remote: Enumerating objects: 483, done.
remote: Counting objects: 100% (67/67), done.
remote: Compressing objects: 100% (57/57), done.
remote: Total 483 (delta 11), reused 0 (delta 0), pack-reused 416
Receiving objects: 100% (483/483), 94.89 MiB | 2.34 MiB/s, done.
Resolving deltas: 100% (112/112), done.
Checking out files: 100% (300/300), done.
keenandr@DESKTOP-RMC6KCH:~$ git remote add github git@github.com:MSU-ICER/hpcc-user-documentation.git^C
keenandr@DESKTOP-RMC6KCH:~$ cd public-documentation/
keenandr@DESKTOP-RMC6KCH:~/public-documentation$ ls
README.md  docs  mkdocs.yml
keenandr@DESKTOP-RMC6KCH:~/public-documentation$ git remote add github git@github.com:MSU-ICER/hpcc-user-documentation.git
keenandr@DESKTOP-RMC6KCH:~/public-documentation$ vi docs/
2018-cluster-resources.md  development-nodes.md       install-ssh-client.md      obtain-an-hpcc-account.md
attachments/               index.md                   job-policies.md            virtual-help-desk.md
keenandr@DESKTOP-RMC6KCH:~/public-documentation$ vi docs/index.md
keenandr@DESKTOP-RMC6KCH:~/public-documentation$ git commit -m "change wording" -a
[main 4a17ad5] change wording
 1 file changed, 1 insertion(+), 1 deletion(-)
keenandr@DESKTOP-RMC6KCH:~/public-documentation$ git push
Counting objects: 4, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 368 bytes | 368.00 KiB/s, done.
Total 4 (delta 3), reused 0 (delta 0)
To gitlab.msu.edu:icer/public-documentation.git
   47418e1..4a17ad5  main -> main
```
-->

Once you've completed your changes, don't forget to commit with `git add` / `git commit` / `git push` to move the markdown files back to this repository. 

## Tags usage

There is a tag manager mkdocs add-in/extension.  Tags should be added to the top of a docs page with

```
---
tags: ["tag name", "tag two name"]
---
```

Tags should be short and descriptive. Check if the tag you want exists already in the tags index page. Pages will be automatically added to the tag index once tagged.

### Tag index pages

To create a tag index page, or add a tag index to an existing page, add the page to mkdocs.yml:

```
tags_extra_files:
    your_tag_index_file.md:
        - your_tag_identifier
```

`- your_tag_identifier` limits the tags displayed to those that share the identifier. 

To add an identifier, or add tags to an existing identifier (and thus its index page), edit:

```
extra:
  tags:
    tag name: tag_identifier
    tag two name: tag_identifier_two
    tag three name: tag_identifier
```

Note that multiple tags can have the same identifier.

For more information see <https://squidfunk.github.io/mkdocs-material/setup/setting-up-tags>

## Redirects

If we need to rename a .md file, we can preserve external links to that page
using a redirect. The process is:

- Rename the file
- Rename all *internal* docs links to the file
- Add the file to the redirect map in mkdocs.yml as:
"old_name.md": "new_name.md"

## Optional Google feedback form link

There are stubs to be able to include feedback icons on every page (*was this page helpful?).  That can be linked via a custom Google Form but you have to create that.   The form should be prefilled using the URL specified in `mkdocs.yml`, under the extras -> analytics section.  For ICER personnel, an example form used by ICER docs is here: <https://docs.google.com/forms/d/1MeWSPYliSxigA8BRgsexYmiXq8ULqWf7LMb35hi5jxo/edit>

This is completely optional and depends up on your project. 

This form used by ICER Docs can create an issues, so this is also possible.  The creation of issues is handled by a Google Apps Script. It is part of the Google Sheet that the Form points to. You can view the Apps Script under Extensions -> Apps Script in the Sheet. 

For ICER docs, the script reads the latest row from the sheet every time the form is filled, and sends it to the MSU Gitlab instance via the [Gitlab Issues API](https://docs.gitlab.com/ee/api/issues.html) with an Access Token. The Access Token may need to be recreated periodically if Gitlab changes its authentication requirements. To view the access tokens and create new ones, see Settings -> Access Tokens here on Gitlab.

