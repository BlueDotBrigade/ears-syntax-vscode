# How To: Create VS Code Extension

## Background

- VS Code supports writing custom TextMate-based [syntax highlighting][Syntax Highlight Guide].
	- It also supports semantic highlighting which is a layer built on top of syntax highlighting.
	- Semantic highlighting is not required in order to implement an EARS highlighter.

## Creation

1. Open a *bash* terminal in VS Code.
2. `npm install -g yo generator-code`
3. Start the *Yeoman* extension using:
	- `yo code`
4. Select *New Language Support*
5. Provide the following information:
	- Language Id: `ears`
	- Language Name: `EARS`
	- File Extensions: `ears`
	- Description: `EARS Language Support`
	- Root Scope: `source.ears`
	- First Line Match: `^#EARS`
6. *Yeoman* will create a new directory named `ears` in the current VS Code directory.
7. Update the `*.tmLanguage.json` file with RegEx `patterns` that match the EARS syntax.
	- See [Syntax Highlight Guide][] for more information.

## Deployment

### Using a Package

1. Open a *bash* terminal in VS Code.
2. If you haven't done so already, install:
	- `npm install -g vsce`
3. Create a package using
	- `vsce package`
4. Copy the `*.vsix` package to the target computer.
5. VS Code => Extensions => More Actions (`...`) => Install from VSIX...

### Using Microsoft Marketplace



## Additional Reading

- [Your First Extension][]
- [Syntax Highlight Guide][]
	- Tool: [Inspect Editor Tokens and Scopes][]

[Your First Extension]: https://code.visualstudio.com/api/get-started/your-first-extension
[Syntax Highlight Guide]: https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide
[Inspect Editor Tokens and Scopes]: https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide#scope-inspector
[Publishing Extensions]: https://code.visualstudio.com/api/working-with-extensions/publishing-extension#verify-a-publisher