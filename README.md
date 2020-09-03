# EmployeeTraining

Employee training documents for sforzando LLC. and Inc.

## Requirements

- Keynote

## Font

Extract `./font/*.tar.xz` .

```shell
find ./ -type f -name "*.tar.xz" -exec tar Jxvf {} \;
```

## Export presentation documents from Markdown files

### In GitHub Actions automatically

Download from Artifacts on Actions.
![Download from Artifacts](https://user-images.githubusercontent.com/40506652/92154491-d40b4180-ee60-11ea-99e9-0565f3bacc3f.png)

### In VS Code manually

1. Install extension of Marp for VS Code
   - [Marp for VS Code - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)
1. Open Markdown File with Visual Studio Code
1. Open Command Palette and run `Marp: Export slide deck..`
1. then presentation document exported
