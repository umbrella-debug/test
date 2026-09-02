Get-Service MSSQL* | Select Name,Status,StartType

Start-Service 'MSSQL$CONTPAQI'
Set-Service 'MSSQL$CONTPAQI' -StartupType Automatic
Start-Service 'SQLBrowser'

sqlcmd -S HOST-NUC-1\CONTPAQI -U sa -P "<tu_password>" -Q "SELECT @@VERSION"
