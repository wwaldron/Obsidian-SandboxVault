---
authors:
  - Will Waldron
---

# Will Waldron's Obsidian Starter Vault

Welcome to my [Obsidian](https://obsidian.md/) Template/Sandbox vault. If you are unfamiliar with Obsidian then it would be worthwhile to familiarize yourself with their [help documents / documentation](https://help.obsidian.md/). Obsidian is based off of plain text Markdown files (extension `.md`). If you are unfamiliar with Markdown then you should know that Markdown files can be read/opened by any app/software on your device that can read text files.[^1] If you find the idea of learning a formatted text schema then there are a number of resources that can help you.

1. Obsidian has a command palette (opened in the left-hand button menu or by pressing `Ctrl/Cmd + p`) that has ways to insert any Markdown feature (*e.g,*, lists or tables).
1. There are Markdown guides all over the internet that can help you learn the syntax (my go-to guide is conveniently called [The Markdown Guide](https://www.markdownguide.org/)).
1. There are many people on YouTube that can help you get started with Markdown/Obsidian (I learned from [Nick Milo - Linking Your Thinking](https://youtu.be/z4AbijUCoKU?si=ouopvg-cWIZcZyNx))

## Quick Introduction to Obsidian

Obsidian is built around "wikilinks" that are essentially quick links to other files in your Vault. To link to another file, simply open a set of double square brackets `[[]]`. This will open up a dropdown menu where you can link to existing files or drop in new text that will link to a file that has not yet been created. For example, I can link to the [[Physics]] file (`[[Physics]]` under the hood) with square brackets for quick linking between notes/ideas.

### Folders and Tags

Many people who take notes throughout life discuss how difficult it is to categorize notes into folder. However, you will see in the file tree of this Vault that I have a loose set of folders setup that follows [Nick Milo's ACE Folder Framework](https://www.linkingyourthinking.com/lytcon-2023/nick-milo) detailed below.

| Folder    | Files in Folder                                                 |
| --------- | --------------------------------------------------------------- |
| Incoming  | Files yet to be sorted (where new files are created by default) |
| Atlas     | Place / Idea oriented files                                     |
| Calendar  | Time oriented files (*e.g.*, daily notes, meetings)             |
| Efforts   | Current projects and their related files                        |
| Archive   | Files not currently needed (instead of sending to trash)        |
| Templates | For file type structures                                        |

Unfortunately, it is often difficult to know how to sort your files as they come into your Vault which is where tags come in. Tags are created inline with the `#` symbol or listed in the properties of the file and are another way to organize your notes. For example, this paragraph is tagged with the `#ReadMe` tag which will link it to anywhere else in my vault that uses that tag. #ReadMe

### Properties and Bases

Obsidian allows the addition of [YAML](https://yaml.org/) properties at the head of the file (note that I have hidden properties by default). Properties allow you to add metadata to your files that make them easily searched/sorted later.

Recently, Obsidian released a feature called "[Bases](https://help.obsidian.md/bases)" that allows for convenient organization of your notes based on their properties. See the [[Books.base|Books]] base file for an example that sorts based on metadata or below for a base that lists all the files in the templates folder.

```base
properties:
  file.name:
    displayName: File Name
  file.size:
    displayName: File Size (bytes)
views:
  - type: table
    name: Table
    filters:
      and:
        - file.path.startsWith("5 - Templates")
    order:
      - file.name
      - file.size

```

### Third Party Plugins

This template Vault comes with several installed / enabled 3rd Party Plug-Ins (see below).


| Plug-In         | Status    | Description                                                               |
| --------------- | --------- | ------------------------------------------------------------------------- |
| Bible Reference | Enabled   | Easy referencing of Bible passages                                        |
| Book Search     | Enabled   | Easy creation of Book notes (search "Create Book" in the command palette) |
| Dataview        | Installed | Javascript note organization                                              |
| Excalidraw      |           |                                                                           |


[^1]: Many people who choose Obsidian do so because they want to always be able to read their files. That is to say, if Obsidian ceases to exist, you will still be able to read the files made in Obsidian using any other text program.
