# Commvault PowerShell Tools Repository

This repository contains PowerShell scripts and utilities for working with the Commvault PowerShell Module.

## Structure

- `tools/` - PowerShell scripts and utilities
- `README.md` - Project overview and usage
- `.gitignore` - Ignore files for Git

## Getting Started

1. Install the Commvault PowerShell Module (see instructions below).
2. Clone this repository.
3. Use the scripts in the `tools/` directory as needed.

## Example Usage

```powershell
# Import the Commvault module
Import-Module Commvault

# Run a script from the tools directory
./tools/Get-CVClientList.ps1
```

## Requirements

- Commvault PowerShell Module
- PowerShell 5.1 or later

## Installing the Commvault PowerShell Module

To deploy the Commvault PowerShell module, follow these steps:

### Prerequisites

- Microsoft PowerShell 5.1 or later
- Access to the CommCell environment with a Web Server

### Installation Steps

1. Go to the Commvault PowerShell SDK page on the Commvault GitHub repository.
2. Click the **Code** button, then click **Download ZIP** to download the `CVPowershellSDK-master` zip file.
3. Extract the `CVPowershellSDK-master` file to a folder (e.g., `C:\Users\<user>\Downloads\CVPowershellSDK-master`).
4. Launch a PowerShell session (run as Administrator for all-users install).
5. Navigate to the extracted folder.
6. Run the installation command:

    - For online mode:

        ```powershell
        .\Install-CVModules.ps1 -Scope AllUsers
        # or
        .\Install-CVModules.ps1 -Scope CurrentUser
        ```

    - For offline mode:

        ```powershell
        .\Install-CVModules.ps1 -Scope AllUsers -Offline
        # or
        .\Install-CVModules.ps1 -Scope CurrentUser -Offline
        ```

    - To persist module path:

        ```powershell
        PersistModulePath $env:PSModulePath
        ```

### Verifying Installation

After installation, you can verify the module is available:

```powershell
Get-Module -ListAvailable Commvault
```

### Connecting to CommCell

To run Commvault cmdlets, log on to the CommServe host:

```powershell
Connect-CVServer
```

Refer to the PDF in the `docs/` folder for more details and troubleshooting.

## Contributing

Feel free to submit issues or pull requests for new scripts or improvements.
