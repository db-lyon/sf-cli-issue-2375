## Steps to Reproduce:

1. git clone https://github.com/db-lyon/sf-cli-issue-2375.git
2. run `sf package version create --package 0HoJx00000000WHKAY -x`

## Expectation:
1. New Package Version is created

## Reality: 

1. See output:

```

PS C:\Users\david\Projects\sf-cli-issue-2375> sf package:version:create:report -i 08cJx0000000OyPIAU
 »   Warning: Plugin @salesforce/plugin-packaging (2.1.11) differs from the 
 »   version specified by sf (2.1.7)
=== Package Version Create Request

 Name                          Value
 ───────────────────────────── ────────────────── 
 ID                            08cJx0000000OyPIAU
 Status                        Error
 Package Id                    0HoJx00000000WHKAY
 Package Version Id
 Subscriber Package Version Id
 Tag
 Branch
 Created Date                  2024-02-28 12:44
 Installation URL
 Created By                    005Jx0000010IkLIAU
 Converted From Version Id     ID Unavailable

=== Errors

Warning: (1) TEST: invalid cross reference id
```



# Negative test:

## Steps to Reproduce:

1. git clone https://github.com/db-lyon/sf-cli-issue-2375.git
2. DELETE the `<externalCredentialPrincipalAccesses>` member from `TEST.permissionset-meta.xml`
3. run `sf package version create --package 0HoJx00000000WHKAY -x`

## Expectation:
1. New Package Version is created

## Reality: 
1. New Package Version is created


latest version info:

```json
PS C:\Users\david\Projects\sf-cli-issue-2375> sf version --verbose --json
{
  "architecture": "win32-x64",
  "cliVersion": "@salesforce/cli/2.31.7",
  "nodeVersion": "node-v18.18.1",
  "osVersion": "Windows_NT 10.0.22621",
  "rootPath": "C:\\ProgramData\\nvm\\v18.18.1\\node_modules\\@salesforce\\cli",
  "shell": "cmd.exe",
  "pluginVersions": [
    "@oclif/plugin-autocomplete 3.0.11 (core)",
    "@oclif/plugin-commands 3.1.6 (core)",
    "@oclif/plugin-help 6.0.14 (core)",
    "@oclif/plugin-not-found 3.0.12 (core)",
    "@oclif/plugin-plugins 4.2.5 (core)",
    "@oclif/plugin-search 1.0.17 (core)",
    "@oclif/plugin-update 4.1.14 (core)",
    "@oclif/plugin-version 2.0.12 (core)",
    "@oclif/plugin-warn-if-update-available 3.0.12 (core)",
    "@oclif/plugin-which 3.1.1 (core)",
    "@salesforce/cli 2.31.7 (core)",
    "apex 3.0.26 (core)",
    "auth 3.3.17 (core)",
    "data 3.1.6 (core)",
    "deploy-retrieve 3.2.20 (core)",
    "info 3.0.28 (core)",
    "limits 3.1.12 (core)",
    "marketplace 1.0.26 (core)",
    "org 3.4.0 (core)",
    "packaging 2.1.11 (user)",
    "schema 3.1.6 (core)",
    "settings 2.0.29 (core)",
    "sobject 1.1.15 (core)",
    "source 3.1.16 (core)",
    "telemetry 3.1.14 (core)",
    "templates 56.0.19 (core)",
    "trust 3.3.14 (core)",
    "user 3.3.0 (core)",
    "@salesforce/sfdx-scanner 3.21.0 (user)"
  ]
}
```
