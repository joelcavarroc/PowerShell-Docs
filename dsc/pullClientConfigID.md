# Setting up a pull client using configuration ID

> Applies To: Windows PowerShell 5.0

Each target node has to be told to use pull mode and given the URL where it can contact the pull server to get configurations. To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information. To configure the LCM, you create a special type of configuration, derated with the **DSCLocalConfigurationManager** attribute. For more information about configuring the LCM, see [Configuring the Local Configuration Manager](metaConfig.md).

> **Note**: This topic applies to PowerShell 5.0. For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)

The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = 1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            
        }      
    }
}
PullClientConfigID
```

In the script, the **ConfigurationRepositoryWeb** block defines the pull server. The **ServerURL**

After this script runs, it creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there. In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.

To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file. For example: `Set-DSCLocalConfigurationManager localhost –Path .\PullClientConfigID –Verbose.`

## Configuration ID

The script sets the **ConfigurationID** property of LCM to a GUID that had been previously created for this purpose (you can create a GUID by using the **New-Guid** cmdlet). The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server. The configuration MOF file on the pull server must be named _ConfigurationID_.mof, where _ConfigurationID_ is the value of the **ConfigurationID** property of the target node's LCM.

## SMB pull server

To set up a client to pull configurations from an SMB server, use a **ConfigurationRepositoryShare** block. In a **ConfigurationRepositoryShare** block, you specify the path to the server by setting the **SourcePath** property. The following metaconfiguration configures the target node to pull from an SMB pull server named **SMBPullServer**.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb SMBPullServer
        {
            SourcePath = '\\SMBPullServer\PullSource'
            
        }     
    }
}
PullClientConfigID
```

## Resource and report servers

By default, the client node gets required resources from and reports status to the configuration pull server. However, you can specify different pull servers for resources and reporting.
To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).
To specify a report server, you use a **ReportRepositoryWeb** block. A report server cannot be an SMB server.
The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**, and to send status reports to **CONTOSO-ReportSrv**.

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            
        }
        
        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-ResourceSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-ResourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

## See Also

* [Setting up a pull client with configuration names](pullClientConfigNames.md)
