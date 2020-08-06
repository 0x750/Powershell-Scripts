# New Login

Set the `Execution Policy` to `RemoteSigned` :

```powershell
Set-ExecutionPolicy RemoteSigned
```

Open a new window to get the user credential and store it in the `$UserCredential` variable :

```powershell
$UserCredential = Get-Credential
```

Change domain after `DelegatedOrg=` to connect to Exchange server : 

```powershell
$Session = New-PSSession`
 -ConfigurationName Microsoft.Exchange`
 -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=tenant.onmicrosoft.com`
 -Credential $UserCredential`
 -Authentication Basic -AllowRedirection
```

Then, import the `$Session` to run commands :

```powershell
Import-PSSession $Session
```

To exit and remove the `$Session` :

```powershell
Remove-PSSession $Session
```
