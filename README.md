# Your Massive Wiki

Version 2023-07-21-001.

## What This Repo Is For

If you're seeing this on GitHub, click "Use this template" to make your own copy of this repo. Or, you can create a fork, or just clone this repo any other way.

This repo is great to start with if you'll ever want to use Massive Wiki Builder to publish your wiki to the web. If you don't need that capability, you can usually just start a Massive Wiki with an empty directory and Git and your favorite Markdown editor.

## For Editing Wiki Files

Welcome to the home page of this wiki. Edit to make it your own! You can delete all the sample content on this page, and replace it with yours.

Use Markdown, or just type text -- either way works.

Use double square brackets around words to make links to other pages in this wiki. [Obsidian](https://obsidian.md), [logseq](https://logseq.com/), are two of many applications that support this kind of linking.

## For Publishing Wiki To Website

**THIS FOLLOWING IS AN ADVANCED TOPIC.** You do not need the following information if you just want to edit your wiki.

### Getting Started

- install [Python](https://www.python.org/downloads/) minimum version
  3.8 but latest should work  
- `$ cd <your-massive-wiki-starter-directory>`  
- initialize and update the Massive Wiki Builder (MWB) and Massive Wiki Themes submodules  
  `$ git submodule init`  
  `$ git submodule update --remote --merge`  
  `$ cd .massivewikibuilder/massivewikibuilder`  
- one recommended practice to keep MWB Python code local to this wiki  
  `$ python3 -m venv venv`  
  `$ source venv/bin/activate`  
  `(venv) $ pip install --upgrade pip`  
  `(venv) $ pip install -r requirements.txt`
- enable full-text search on the MWB generated website (may require `npm` update)  
- `$ npm ci`  
- build:  
- `(venv) $ ./mwb3.py -c ../mwb.yaml -w ../.. -o ../output -t ../this-wiki-themes/basso --lunr`  
- run your local web server on the `.massivewikibuilder/massivewikibuilder/output` folder

### Install and Use Notes

You can use [Massive Wiki Builder](https://github.com/peterkaminski/massivewikibuilder) to publish (export) any Massive Wiki to static HTML files. The wiki is then in a format viewable by anyone with a web browser.

If your website host has build automation, you can adapt the included `netlify.toml` file and the build automation should automatically use the Git submodule mechanism to retrieve the MWB code it needs.

Massive Wiki Builder (MWB) and [Massive Wiki Themes](https://github.com/peterkaminski/massive-wiki-themes) are included in this repo as Git submodules.

If you are using MWB locally on your computer, you will need to retrieve MWB, and optionally, the themes. One way to do this is shown above.

Note: When the upstream Massive Wiki Builder or Massive Wiki Themes repos have been updated, your submodules won't automatically update. Conceptually, they are "pinned" to the Git hash you set them up with.

To upgrade your submodules to the latest upstream version, you can use these commands:

```shell
$ cd .massivewikibuilder
$ git submodule init
$ git submodule update --remote --merge massivewikibuilder
$ git submodule update --remote --merge massive-wiki-themes
```

After that, `git status` will show that there have been changes to the submodules. Use your regular add, commit, and push process to update your repo.

See the [Submodules chapter of the Git Book](https://git-scm.com/book/en/v2/Git-Tools-Submodules) for more information about Git submodules.

### Themes

This starter wiki is set up with two MWB / MWT themes, Alto and Basso, in the `.massivewikibuilder/this-wiki-themes` folder. We suggest you continue to use and customize your wiki's themes in the `.massivewikibuilder/this-wiki-themes` folder.

The Massive Wiki Themes repo is updated from time to time, and when you refresh your local Git submodule in `.massivewikibuilder/massive-wiki-themes`, you will receive those updates. Rather than use those themes directly, though, it is suggested to copy what you want into your `this-wiki-themes` folder, and customize and use your copy of the themes from there.

After you update `massive-wiki-themes`, you can compare (with `diff` or another tool) the upstream theme in `massive-wiki-themes` and your customized version of it in `this-wiki-themes`, and port over any changes you want.
