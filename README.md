rsNTFSPermissions
=================

A Powershell DSC module to manage NTFS permissions based on Alisdair Craik's code on http://www.vexasoft.com/blogs/powershell/9561687-powershell-4-desired-state-configuration-enforce-ntfs-permissions

```powershell
Configuration SampleNTFSConfig
{
    Node MyComputer
    {
        NTFSPermission Permission1
        {
            Ensure = "Present"
            Account = "MyUser"
            Access = "Allow"
            Path = "c:\MyDirectory"
            Rights = "ReadAndExecute"
        } 
    }
}

SampleNTFSConfig
Start-DscConfiguration -Wait -Verbose -Force .\SampleNTFSConfig -ComputerName MyComputer
```
