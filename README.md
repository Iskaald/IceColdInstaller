# IceCold Module Installer

![Unity Version](https://img.shields.io/badge/Unity-2021.3%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)

A custom Unity editor tool designed to simplify the management of "IceCold" modules within your project. It allows you to easily browse, install, update, and remove custom packages directly from a central repository.

## Features

-   **Automatic First-Time Setup**: The installer window opens automatically the first time it's imported into a project.
-   **Central Module Browser**: View all available modules, their descriptions, and dependencies in one clean interface.
-   **One-Click Actions**: Install, Update, Downgrade, or Uninstall modules with a single button click.
-   **Automatic Dependency Resolution**: When you install a module, the installer automatically detects and offers to install any required dependencies.
-   **Version Management**: Clearly see which version of a module is installed and easily switch between available versions.
-   **Safe Uninstallation**: Prevents you from uninstalling a module that other installed modules depend on.
-   **Quick Utilities**: Includes menu items for creating standard project folder structures and manually refreshing packages.

## Installation

### Recommended: Unity Package Manager (via Git URL)

This is the cleanest and recommended way to install the package. It keeps the package isolated in your `Packages` folder and makes updates easy.

1.  In your Unity project, open the **Package Manager** window (`Window > Package Manager`).
2.  Click the **`+`** icon in the top-left corner and select **"Add package from git URL..."**.
3.  Paste the following URL and click **Add**:
    ```
    https://github.com/Iskaald/IceColdInstaller.git
    ```
### Manual Installation

If you prefer, you can install the package manually.

1.  Download the latest release `.zip` file from the [Releases page](https://github.com/Iskaald/IceColdInstaller/releases).
2.  Unzip the file.
3.  Copy the entire `IceColdInstaller` folder into your project's `Assets` or `Packages` directory.

## Getting Started

### First-Time Use

Upon successful installation, the **IceCold Installer** window will automatically open. This only happens once per project.
Click `Setup` on the Installer's bottom bar to create a necessary folder structure.

### Manual Use

If you close the window, you can reopen it at any time by navigating to the Unity menu:

**`IceCold > Installer`**

 <!-- It's highly recommended to add a screenshot of your menu item here -->

## How to Use the Installer

The installer window provides a list of all available modules.

 <!-- Add a screenshot of the main window -->

1.  **Browse Modules**: Scroll through the list to find the module you need. Each module displays:
    -   Its **Display Name** and **Description**.
    -   A list of its **Dependencies**. Dependencies shown in <span style="color:#E07B53">**orange**</span> are not yet installed in your project.

2.  **Select a Version**: Use the **Version** dropdown to select which version of the module you wish to install. It defaults to the latest version.

3.  **Check Installed Version**: The **"Installed Version"** field tells you which version, if any, is currently in your project.

4.  **Perform an Action**: The action button will change based on the current state:
    -   **Install**: If the module is not in your project.
    -   **Update/Downgrade**: If you select a version different from the one installed.
    -   **Uninstall**: If you have the same version selected as the one that is installed.

### Bottom Bar

-   **Version Number**: Displays the current version of the installer tool itself.
-   **Setup**: Creates a folder structure for configs used by IceCold modules.
-   **Check for Updates**: Clicks this to automatically pull the latest version of the installer tool from its Git repository.
-   **Refresh**: Manually re-fetches the module list and re-scans your project's `manifest.json` file. Useful if you've made manual changes.

## How It Works

This tool works by fetching a list of available modules from a central `modules.json` file hosted on GitHub. When you choose to install or uninstall a module, the installer modifies your project's `Packages/manifest.json` file and then prompts Unity's Package Manager to resolve the changes, which handles the actual downloading and importing of the package.

## Troubleshooting

-   **Installer window doesn't open automatically:** Check the Unity Console for any script compilation errors. You can always open it manually via `IceCold > Installer`.
-   **Modules list is empty or fails to load:** Ensure you have a stable internet connection. If the problem persists, the remote `modules.json` file might be temporarily unavailable.
-   **A package fails to install/resolve:** Check the Unity Console for detailed error messages from the Package Manager. It often provides clues about dependency conflicts or incorrect Git URLs. Try using the `Refresh` button in the installer.

---

## License

This project is licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.
