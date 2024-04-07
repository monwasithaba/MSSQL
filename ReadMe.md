Create SQL Server Docker container
=======================================================

docker run -e "ACCEPT_EULA=Y" -e 'SA_PASSWORD=P@$$w0rd1' -e 'MSSQL_PID=Express' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2019-latest

docker exec -it sql1 /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P "P@$$w0rd1" -Q "ALTER LOGIN SA WITH PASSWORD='<YourNewStrong@Passw0rd>'"

$ docker exec -it <containerName> /opt/mssql-tools/bin/sqlcmd -S localhost


Connect to the SQL Server
=======================================================

In the appsettings.json file

"CodePulseConnectioString": "Server=localhost; Initial Catalog=CodePulselDB; User Id=sa; Password=P@$$w0rd1; TrustServerCertificate=true;"