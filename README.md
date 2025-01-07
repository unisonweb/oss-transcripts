# Unison OSS libraries

This repository contains transcripts and transcript outputs that mirror popular OSS Unison libraries from [Unison Share](https://share.unison-lang.org/) to Github, for better discovery and ingestion by AI models. These libraries are open source and written by many excellent developers in the Unison community (see [CONTRIBUTORS](./CONTRIBUTORS)).

## Repository purpose

All contributions to this library from the Unison community are opt-in, with the consent of community authors. Because Unison code is stored in a binary format and hosted on Unison Share, support for AI coding assistants like Copilot has been limited, making it difficult for new users to learn and write Unison programs.

## Adding a library

1. Create a new directory in the `src` folder for your Unison Share username and your library name. It should look like `src/username/library-name`.
2. Create a [Unison transcript file](https://www.unison-lang.org/docs/tooling/transcripts/) called, `scratch.u.md`, in the new directory for your library

[Here's a sample transcript](.github/add_oss_library_template.md) which you can use as a template:

`````
# <Library name>

Short description of what this library does.

## Library contents list

This section contains a `ucm` transcript block that pulls the desired library version and lists its contents with the `find` command.

``` ucm
@unison/base/main> pull.without-history @unison/base/releases/3.28.1
@unison/base/main> find
```

## Code examples

The `find` command in the previous section will have listed the contents of the library, take note of the last numbered argument in the list and use it in the `edit` command below.

``` ucm
@unison/base/main> edit 1-8000
```

## Code style conventions

If your library has specific naming or code style conventions that may be useful for code-completion agents to follow, for example, "everything prefixed with an underscore in this library should be considered an implementation detail", please mention them here.
`````

3. Run the `ucm transcript` command from the root of this project to generate Unison code from the transcript file:

``` bash
$ ucm transcript src/<share-handle>/<library-name>/scratch.u.md
```

This will generate a file called `src/<share-handle>/<library-name>.scratch.u.output.md`.

4. Add your information to the [`CONTRIBUTORS`](./CONTRIBUTORS) file in the root of this repository. Commit and push your changes to a new branch and open a pull request.

## License

This project is licensed with an MIT license, see the [LICENSE](./LICENSE) file for details.