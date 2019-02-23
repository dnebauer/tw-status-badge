---
title:  "Packaging plugin: status-badge"
author: "David Nebauer"
date:   "23 February 2019"
style:  [Standard, Latex14pt]
        # Latex8-12|14|17|20pt; PaginateSections; IncludeFiles
---

# Packaging tiddlywiki plugin "Status Badge" #


## Credit ##

This is a packaging of macros made available by Mohammad Rahmani at
[https://kookma.github.io/status-badge/](). The plugin readme tiddler is a
slight edit of the Mohammad Rahmani's original
[demo](https://kookma.github.io/status-badge/#.mr%2Fdemo%2Fdbadge) tiddler.

## Ensure correct tiddlywiki setup ##

These instructions assume tiddlywiki is running under nodejs with tiddlers
saved to individual files rather than a single-file wiki.

These instructions are for packaging the plugin using Tinka
([project](http://tinkaplugin.github.io),
[repository](https://github.com/TinkaPlugin/Tinka)). Ensure the Tinka plugin is
installed in the tiddlywiki -- this requires restarting the tiddlywiki server
after installing the plugin.

## Uninstall the previous version ##

Skip this section if the plugin is not currently installed in the tiddlywiki
you intend to use for packaging.

Follow these steps:

1. Stop the tiddlywiki server.

2. Delete the plugin file which is located in `'<wiki_root>/tiddlers/'` and
   named `'$__plugins_.dtn_status-badge.tid'`.

3. Copy the `*.tid` files from the `'source'` subdirectory to
   `'<wiki_root>/tiddlers'`.

4. Restart the tiddlywiki server.

## Package using Tinka ##

Open _Control Panel_ > _Tinka Plugin Management_ tab > _Create a new Plugin_ tab.

### Step 1: Enter Metadata ###

Enter the following metadata values:

|       Field|Value                                  |
|-----------:|:--------------------------------------|
| Plugin-Type|plugin                                 |
| Plugin Path|\$:/plugins/.dtn/status-badge          |
|      Author|David Nebauer                          |
|      Source|---                                    |
|  Dependents|---                                    |
|        List|readme credits license                 |
|Plugin Title|Status Badges                          |
|     Version|_0.0.1_ or _increment previous version_|
|Core-Version|>=5.1.18                               |

### Step 2: Add Tiddlers ###

Search for the key phrase `status-badge` and select the following tiddlers:

* \$:/plugins/.dtn/status-badge/credits
* \$:/plugins/.dtn/status-badge/license
* \$:/plugins/.dtn/status-badge/macros
* \$:/plugins/.dtn/status-badge/readme
* \$:/plugins/.dtn/status-badge/stylesheet

### Step 3: Package ###

Press the _Package plugin_ button.

Ignore the _Uncaught TypeError: Cannot read property 'ownerDocument' of
undefined_ internal javascript error, restart the tiddlywiki server, and reload
the wiki in your browser.

Warning: the tiddlers selected in Step 2 are deleted when the plugin file is
built.

## Save plugin file ##

Delete any files in the `plugin` subdirectory.

The plugin file is located in `'<wiki_root>/tiddlers/'` and named
`'$__plugins_.dtn_latex-logos.tid'`.

Save a copy of the plugin file to the `plugin` subdirectory.
