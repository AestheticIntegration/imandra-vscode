# Imandra IDE

Imandra is both a programming language and a reasoning engine with which you can analyse and verify properties of your programs. This VSCode plugin allows you to develop files which can be analysed by imandra, and incorporates a specific merlin extension which provides information on underlying types and completions. 

In order to learn more about imandra, please visit the interactive [documentation pages](https://docs.imandra.ai/imandra-docs/).

## System requirements

It is necessary that you have the executables `ocamlmerlin` and  `ocamlmerlin-imandra` installed on your system and visible via your `$PATH` environment variable.

## Functionality

This VSCode extension builds up the existing [OCaml and Reason IDE](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) for Reason and OCaml files.

### Syntax highlighting

This extension provides a syntax highlighting scheme for files with extension `ml,mli` and `re,rei` via the dependency on the [OCaml and Reason IDE](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml). In addition a syntax highlighter is provided for imandra files with extension `iml`, by which the `imandra` language is identified, which provides identifiable syntax highlighting for the extra reasoning related keywords in imandra such as `verify` and `theorem`.

### Merlin functionality

In order to make this extension function correctly, a workspace must be opened. If the workspace contains a file with suffix `iml` then the workspace configuration is automatically updated to apply the `imandra` reader extension for merlin. This merlin reader extension then applies to *all* OCaml, Reason or Imandra files in the workspace. 

At present the `imandra` reader extension for merlin provides:

- basic syntax error highlighting
- type error information
- type information of the underlying `imandra` types
- general syntax completions

![](https://storage.googleapis.com/imandra-assets/images/github/VS_code_documentation_gif/testImandraHover1.gif)

![](https://storage.googleapis.com/imandra-assets/images/github/VS_code_documentation_gif/testImandraCompletion.gif)


### Inherited functionality

All code actions and commands are inherited from the [OCaml and Reason IDE](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) extension, but the behaviour of merlin is specific to imandra.

## Disclaimer

When you open a workspace with an `imandra` file present you will see warnings appear in the `problems` tab. These warnings do not affect the functionality of the extension and we are working to erradicate them. The two which you will see which currently can safely be disregarded are:

- Array has too many items. Expected {0} or fewer
- Value is not accepted. Valid values: "ocaml", "reason"

## Work in progress

Ideally in future versions of the extension we will allow users to specify the reader for merlin depending on the language of the file. Currently all analysable files in the workspace use the `imandra` reader, but in some cases a user might want to use standard merlin to interpret OCaml files (for example).



