# [WMF Release Notes Overview](releasenotes.md)

# [System Requirements](requirements.md)

# [Known Product Incompatibilites](productincompat.md)

# [Installation Instructions](install.md)
# [Uninstallation Instructions](uninstall.md)

# [Feedback](feedback.md)

# [Scenarios Enabled by WMF 5.0]()
## [Just Enough Administration (JEA)](jea_overview.md)
### [Creating and Connecting to a JEA Endpoint](jea_endpoint.md)
### [Reporting on JEA](jea_report.md)

## [Creating Custom Types using PowerShell Classes](class_overview.md)
### [Define Custom Types](class_newtype.md)
### [Declare Base Class](class_base.md)
### [Declare Implemented Interface](class_interface.md)
### [Call Base Class Constructor](class_baseconstructor.md)
### [Call Base Class Method](class_basemethod.md)

## [Improvements in PowerShell Script Debugging](debug_overview.md)
### [Break into Debugger from Running Scripts](debug_breakall.md)
### [Remote File Editing and Debugging in PowerShell ISE](debug_remote.md)
### [Advanced Script Debugging](debug_advance.md)
#### [Runspace Debugging](debug_runspace.md)
#### [Attach to Process hosting PowerShell](debug_process.md)

## [Improvements in Desired State Configuration (DSC)](dsc_improvements.md)
### [Configurations]()
#### [Specifying Cross Node Dependencies](dsc_waitfor.md)
#### [Encrypted MOFs](dsc_encryptedmof.md)
#### [Help support for DSC Configuration](dsc_confighelp.md)
#### [Authoring Improvements using PowerShell ISE](dsc_authoring.md)
#### [Allowance for Identical Duplicate Resources in a Configuration](dsc_identicalduplicate.md)
#### [Import-DscResource keyword supports -moduleversion parameter](dsc_importdscresource.md)
#### [WOW64 support for Configuration Keyword](dsc_wow64.md)
### [Resources]()
#### [Class-based DSC Resources](dsc_classbasedresource.md)
#### [DSC Resource Script Debugging](dsc_resourcedebugging.md)
#### [Automatic RunAs support for DSC Resources](dsc_runas.md)
#### [Side-By-Side Versioning Support for DSC Resources](dsc_sxsresource.md)
#### [New in-box Resources](dsc_newresources.md)
### [Local Configuration Manager]()
#### [Configure Node with Multiple Configuration Fragments](dsc_partialconfig.md)
##### [Support for Mixed RefreshModes](dsc_partialconfig_mixedmode.md)
#### [Configure DSC Engine with New Attribute](dsc_metaconfiguration.md)
#### [Mix and Match of PUSH and PULL modes](dsc_mixedrefreshmode.md)
#### [Detailed information about LCM State](dsc_lcmstate.md)
#### [Frequencies for RefreshMode and ConfigurationMode need not be multiple of each other](dsc_freqnomultiple.md)
#### [Additional Value for RefreshMode Property](dsc_refreshmode.md)
### [Cmdlets]()
#### [Details about Configuration Status](dsc_getconfigurationstatus.md)
#### [Test-DscConfiguration cmdlet supports Reference Configurations](dsc_testconfiguration.md)
#### [Direct Access to DSC Resource Methods](dsc_directaccess.md)
#### [Deliver Configuration Document without Applying](dsc_publishconfig.md)
#### [Remove DSC Documents](dsc_removeconfigdoc.md)
#### [Unified and Consistent State and Status Representation](dsc_statestatus.md)
#### [Set-DscLocalConfigurationManager cmdlet supports -force parameter](dsc_setdsclcm.md)
### [Pull Mode]()
#### [On-demand PULL of DSC Configurations](dsc_updateconfig.md)
#### [Seperation of Node and Configuration Ids](dsc_nodeid.md)
#### [Separation of Configuration, Resource and Report Repositories](dsc_repository.md)
#### [Report Configuration Status to Central Location](dsc_reporting.md)

## [Audit PowerShell Usage using Transcript and Logging](audit_overview.md)
### [Enhanced Transcription Options](audit_transcript.md)
### [Script Tracing and Loggging](audit_script.md)
### [Cryptographic Message Syntax (CMS) cmdlets](audit_cms.md)

## [Software Discovery, Install and Inventory with PackageManagement](oneget_overview.md)
### [PackageManagement Cmdlets](oneget_cmdlets.md)

## [PowerShell Module Discovery, Install and Inventory with PowerShellGet](psget_module_overview.md)
### [Register a PowerShell Repository](psget_psrepository.md)
### [Side-by-Side Version Support on PowerShell 5.0 or newer](psget_modulesxsinstall.md)
### [Installation of Module Dependencies](psget_moduledependency.md)
### [PowerShellGet Cmdlets for Module Management](psget_modulecmdlets.md)

## [PowerShell Script Discovery, Install and Management with PowerShellGet](psget_script_overview.md)
### [PowerShellGet Cmdlets for Script Management](psget_scriptcmdlets.md)

## [New and updated cmdlets based on community feedback ](feedback_cmdlets.md)
### [Symbolic links using Item cmdlets](feedback_symbolic.md)
### [Archive cmdlets](feedback_archive.md)
### [Clipboard cmdlets](feedback_clipboard.md)
### [Convert-String](feedback_convertstring.md)
### [Extract and Parse Structured Objects out of String](feedback_convertfromString.md)
### [Format-Hex](feedback_formathex.md)
### [NoNewLine parameter](feedback_nonewline.md)
### [New-TemproaryFile](feedback_tempfile.md)
### [New-Guid](feedback_newguid.md)
### [Get-ChildItem has -Depth parameter](feedback_getchilditem.md)
### [Updates to FileInfo object](feedback_fileinfo.md)
### [Modules support for declaring version ranges (1.*, etc)](feedback_moduleversionranges.md)

## [Information Stream](informationstream_overview.md)

## [Generate PowerShell Cmdlets based on OData Endpoint](odata_overview.md)

## [Network Switch Management with PowerShell](networkswitch_overview.md)

## [Software Inventory Logging (SIL)](sil_overview.md)

# [Known Issues and Limitations](limitation_overview.md)
## [Desired State Configuration (DSC) Known Issues](limitation_dsc.md)
