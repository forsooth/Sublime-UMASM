# Sublime Text UMASM Syntax Highlighting

Syntax highlighting for Sublime Text for the UMASM (Universal Machine Assembly Language) used in Tufts' COMP-40: Machine Structure & Assembly Language Programming.

# Installation
In a Sublime installation, there exists a `Packages` folder (for example, with the default installation on a modern GNU/Linux system, at `~/.config/sublime-text-3/`). Within this, there should be a directory called `User`; if there is not, then create it. Copy the `UMASM.tmLanguage` file into this directory, and restart sublime; in the `View > Syntax` menu, there should now be an entry called `UMASM`.

# Development & Contributing
This syntax highlighting is not guaranteed to be perfect, as it was originally written in an hour or so while doing this project when I took COMP-40. If you find any issues, please open a GitHub issue and we can address it.

The structure of a Sublime Text syntax highlighting configuration is that there exists a `*.YAML-tmLanguage` file. This is human-readable, and contains a list of patterns in the YAML file format. Each pattern contains:
* a `comment` field describing the use of this match, for readability's sake
* a `name` field, containing the Sublime [scope](https://www.sublimetext.com/docs/3/scope_naming.html) which determies what color the matched characters will appear
* a `match` field listing a regular expression which will be matched. 

The available scopes for the `name` field are predetermined, and are the hooks for which a Sublime theme provides colors. 

The `Package Dev` package for Sublime is recommended for building the syntax highlighting. The `*.tmLanguage` file which is eventually read and interpreted by Sublime is a glorified XML file, and can be significantly more difficult to read. The `Package Dev` package provides a build process from `*.YAML-tmLanguage` to `*.tmLanguage`. Once installed, simply open the `*.YAML-tmLanguage` file and navigate to `Tools > Build Systems > Automatic` before using `Ctrl+B` (a.k.a. `Tools > Build`) to build the final `*.tmLanguage` file.

Note that Sublime Text 3 has since made available a much improved `*.sublime-syntax` file format, but YAML is backwards compatible in case anyone is still using Sublime Text 2.
