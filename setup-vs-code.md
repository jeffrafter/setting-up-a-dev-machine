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
  "window.zoomLevel": 2,
  "editor.renderWhitespace": "all",
  "editor.folding": false,
  "editor.renderControlCharacters": true,
  "editor.minimap.enabled": false,
  "breadcrumbs.enabled": false,
  "workbench.statusBar.visible": true,
  "workbench.colorTheme": "Yoncé",
  "workbench.editor.enablePreview": false,
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
  "C_Cpp.updateChannel": "Insiders",
  "[javascript]": {
    "editor.formatOnSave": false
  },
  "[javascriptreact]": {
    "editor.formatOnSave": false
  },
  "[typescript]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescriptreact]": {
    "editor.formatOnSave": false
  },
  "eslint.alwaysShowStatus": true,
  "cSpell.userWords": [
  ],
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "terraform.indexing": {
    "enabled": false,
    "liveIndexing": false,
    "delay": 500,
    "exclude": [
      ".terraform/**/*",
      "**/.terraform/**/*"
    ]
  },
  "terraform.languageServer": {
    "enabled": true,
    "args": []
  }
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
* /Bracket Pair Colorizer 2/ - https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2
* /Apollo GraphQL/ - https://marketplace.visualstudio.com/items?itemName=apollographql.vscode-apollo
* /Spell Right/ - [Spell Right - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ban.spellright)


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

// Place your key bindings in this file to override the defaultsauto[]
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
