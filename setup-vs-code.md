# Setting up Visual Studio Code
#setup 

Download it
Open the command palette (Shift+Command+P)
Install 'code' command in PATH

Go to Code | Preferences | Settings

View | Command Palette
Preferences: Open Settings (JSON)

```
{
  "editor.renderWhitespace": "all",
  "editor.folding": false,
  "editor.renderControlCharacters": true,
  "editor.stickyScroll.enabled": true,
  "editor.minimap.enabled": false,
  "breadcrumbs.enabled": true,
  "workbench.statusBar.visible": true,
  "workbench.colorTheme": "Yoncé",
  "extensions.ignoreRecommendations": true,
  "editor.tabSize": 2,
  "editor.formatOnSave": true,
  "gitblame.statusBarPositionPriority": 1,
  "gitblame.statusBarMessageFormat": "@${author.name} (${time.ago})",
  "keyboard.touchbar.enabled": false,
  "typescript.updateImportsOnFileMove.enabled": "always",
  "workbench.startupEditor": "none",
  "workbench.colorCustomizations": {
    "editorSuggestWidget.selectedBackground": "#FC43847A"
  },
  "editor.suggestSelection": "first",
  "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
  "[javascript]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[javascriptreact]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescript]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescriptreact]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "eslint.alwaysShowStatus": true,
  "cSpell.userWords": ["Parentheticals"],
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "terraform.indexing": {
    "enabled": false,
    "liveIndexing": false,
    "delay": 500,
    "exclude": [".terraform/**/*", "**/.terraform/**/*"]
  },
  "terraform.languageServer": {
    "enabled": true,
    "args": []
  },
  "editor.inlineSuggest.enabled": true,
  "[python]": {
    "editor.formatOnType": true
  },
  "fountain.pdf.createBookmarks": false,
  "[json]": {
    "editor.defaultFormatter": "vscode.json-language-features"
  },
  "github.copilot.enable": {
    "*": true,
    "plaintext": false,
    "markdown": true,
    "scminput": false
  },
  "window.zoomLevel": 1,
  "window.commandCenter": true,
  "[csharp]": {
    "editor.maxTokenizationLineLength": 2500
  },
  "omnisharp.monoPath": "/Library/Frameworks/Mono.framework/Versions/Current/Commands/mono",
  "omnisharp.useGlobalMono": "always",
  "omnisharp.path": "latest",
  "omnisharp.useModernNet": false,
  "dotnet.inlayHints.enableInlayHintsForParameters": true,
  "dotnet.inlayHints.enableInlayHintsForLiteralParameters": true,
  "dotnet.inlayHints.enableInlayHintsForIndexerParameters": true,
  "dotnet.inlayHints.enableInlayHintsForObjectCreationParameters": true,
  "dotnet.inlayHints.enableInlayHintsForOtherParameters": true,
  "csharp.inlayHints.enableInlayHintsForTypes": true,
  "csharp.inlayHints.enableInlayHintsForImplicitVariableTypes": true,
  "csharp.inlayHints.enableInlayHintsForImplicitObjectCreation": true,
}
```

Extensions:

* /Yonce/ - https://marketplace.visualstudio.com/items?itemName=minamarkham.yonce-theme
* /Ruby/ - https://marketplace.visualstudio.com/items?itemName=rebornix.Ruby
* /VSCode Ruby/ - https://marketplace.visualstudio.com/items?itemName=wingrunr21.vscode-ruby
* /Visual Studio IntelliCode/ - https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode
* /Prettier - Code formatter/ - https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode
* /Open in GitHub, Bitbucket, Gitlab, VisualStudio.com !/ - https://marketplace.visualstudio.com/items?itemName=ziyasal.vscode-open-in-github
* /Markdown All in One/ - https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one
* /Git Blame/ - https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame
* /final-newline/ - https://marketplace.visualstudio.com/items?itemName=samverschueren.final-newline
* /ESLint/ - https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint
* /empty-indent/ - https://marketplace.visualstudio.com/items?itemName=DmitryDorofeev.empty-indent
* /Code Spell Checker/ - https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker
* /Apollo GraphQL/ - https://marketplace.visualstudio.com/items?itemName=apollographql.vscode-apollo
* /Spell Right/ - [Spell Right - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ban.spellright)
* /Rails Run Specs/ - https://marketplace.visualstudio.com/items?itemName=noku.rails-run-spec-vscode (Cmd+L to run the spec at the line, Shift+Cmd+T to run all specs in the file)
* /Python/ - https://marketplace.visualstudio.com/items?itemName=ms-python.python
* /Jupyter/ - https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter

As command line:

```
code --install-extension minamarkham.yonce-theme
code --install-extension rebornix.Ruby
code --install-extension VisualStudioExptTeam.vscodeintellicode
code --install-extension esbenp.prettier-vscode
code --install-extension ziyasal.vscode-open-in-github
code --install-extension yzhang.markdown-all-in-one
code --install-extension waderyan.gitblame
code --install-extension samverschueren.final-newline
code --install-extension dbaeumer.vscode-eslint
code --install-extension DmitryDorofeev.empty-indent
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension apollographql.vscode-apollo
code --install-extension ban.spellright
code --install-extension ms-python.python
code --install-extension ms-vsliveshare.vsliveshare
code --install-extension hashicorp.terraform
code --install-extension tonybaloney.vscode-pets
```


Setup VSCode for git:

```
git config --global core.editor "code --wait --new-window"
```


Set it up for diff:

Run: `git config --global -e`

```
[diff]
    tool = default-difftool
[difftool "default-difftool"]
    cmd = code --new-window --wait --diff $LOCAL $REMOTE
```

Open command pallete and choose: Open Keyboard Settings (JSON)

```
// Place your key bindings in this file to override the defaults
[
  {
    "key": "cmd+t",
    "command": "workbench.action.quickOpen"
  },
  {
    "key": "cmd+p",
    "command": "-workbench.action.quickOpen"
  },
]
```

> Note: `.env` files won't quick open by default because they are ignored in the `.gitignore` which is used to exclude files. Open it once manually and then it will be quick-openable because it was "recently opened"

# Unity

- https://code.visualstudio.com/docs/other/unity
- https://vscode.readthedocs.io/en/latest/other/unity/

Open Unity Preferences, External Tools, choose files to edit in Visual Studio Code

```
brew install mono
```

Set omnisharp Use Global Mono to always.