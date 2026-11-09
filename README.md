# VS Code Configuration

My personal Visual Studio Code config, including custom UI styling.

## Repository Structure

```text
vscode-config/
├── vscode/
│   ├── settings.json
│   ├── keybindings.json
│   ├── extensions.txt
│   └── styling/
│       ├── custom.css
│       └── custom.js
│
└── README.md
```

## Requirements

- [Visual Studio Code](https://code.visualstudio.com/)
- [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css)

## Setup

### 1. Install Extensions

Install all extensions listed in `vscode/extensions.txt`:

```powershell
Get-Content .\vscode\extensions.txt | ForEach-Object {
    code --install-extension $_
}
```

### 2. Apply VS Code Settings

Copy `vscode/settings.json` into your VS Code user settings directory.

On Windows:

```text
%APPDATA%\Code\User\settings.json
```

Alternatively, open the Command Palette (`Ctrl + Shift + P`), select **Preferences: Open User Settings (JSON)**, and copy the configuration across.

### 3. Apply VS Code Keybindings

Copy `vscode/keybindings.json` into your VS Code user settings directory.

On Windows:

```text
%APPDATA%\Code\User\keybindings.json
```

Alternatively, open the Command Palette (`Ctrl + Shift + P`), select **Preferences: Open Keyboard Shortcuts (JSON)**, and copy the configuration across.

### 4. Configure Custom CSS and JavaScript

The custom CSS and JavaScript files use the **Custom CSS and JS Loader** extension.

Add the following to your VS Code `settings.json`:

```json
"vscode_custom_css.imports": [
    "file:///absolute/path/to/vscode/styling/custom.css",
    "file:///absolute/path/to/vscode/styling/custom.js"
]
```

Replace the paths with the actual locations of the files.

For example, on Windows:

```json
"vscode_custom_css.imports": [
    "file:///C:/Users/somedev/vscode-config/vscode/styling/custom.css",
    "file:///C:/Users/somedev/vscode-config/vscode/styling/custom.js"
]
```

Once configured:

1. Open the Command Palette (`Ctrl + Shift + P`).
2. Run **Enable Custom CSS and JS**.
3. Restart VS Code if prompted.

**Note:** This extension modifies VS Code's installation files to inject custom styling and JavaScript. VS Code may display a corrupt installation warning. Updates can overwrite these modifications, requiring you to re-enable the extension.

## Updating Extensions

To regenerate the installed extension list:

```powershell
code --list-extensions > .\vscode\extensions.txt
```

## Theme and Styling

I use [Aura Dark](https://marketplace.visualstudio.com/items?itemName=DaltonMenezes.aura-theme) by [Dalton Menezes](https://github.com/daltonmenezes), with personal colour and UI customisations.

The custom CSS and JavaScript were developed using this [YouTube tutorial](https://www.youtube.com/watch?v=9_I0bySQoCs) as a baseline, then adapted to suit my taste.

Customisations include:

- Teal accent colours used more broadly.
- Centralised Command Palette view with blurred background.
- Modified editor tabs and sidebar selection/hover colours.
- Customised integrated terminal palette.
- Minimalist title bar.

## Credits

- **Aura Dark theme:** Original theme by Dalton Menezes. This repository contains personal configuration modifications and is not affiliated with or endorsed by the original author.
- **Custom CSS/JS:** The linked YouTube tutorial was used as a starting point and reference for the custom UI modifications.
