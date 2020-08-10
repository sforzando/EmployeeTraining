# EmployeeTraining

Employee training documents for sforzando LLC. and Inc.

## Requirement

- Keynote
- Visual Studio Code
  - [Marp for VS Code - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)

## Font

Extract `./font/*.tar.xz` .

```shell
find ./ -type f -name "*.tar.xz" -exec tar Jxvf {} \;
```

## Export PDF from .md

1. Open Markdown File with Visual Studio Code.
1. Open Command Palette and run `Marp: Export slide deck..` .
1. then PDF exported.
