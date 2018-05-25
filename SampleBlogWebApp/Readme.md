Below are the docker commands used for application and SQL Server containerization:

   docker build -t sampleblogwebapp .

   docker run -d -p 80:80 --name sampleblogwebapp-anubhav sampleblogwebapp

   docker pull microsoft/mssql-server-windows-express

   Invoke-WebRequest https://dl.bintray.com/docker-compose/master/docker-compose-Windows-x86_64.exe -UseBasicParsing -OutFile $env:ProgramFiles\docker\docker-compose.exe

   docker run -d -p 1433:1433 --name sqlserverblog-anubhav -v sql-data:C:/temp/ -e attach_dbs="[{'dbName':'Blogging','dbFiles':['C:\DB\Blogging.mdf','C:\DB\Blogging_log.ldf']}]" -e       sa_password=Testing123456 -e ACCEPT_EULA=Y microsoft/mssql-server-windows-express

   docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" sampleblogwebapp-anubhav


Commands  to execute SQL script to have database ready. 

    docker exec -it sqlserverblog-anubhav sqlcmd
    
    Once connected to database server, executed Blogging.sql script to create table and insert records.
    
    SQL script is placed at location: ..\SampleBlogWebApp\SampleBlogWebApp\Blogging.sql


Command to run docker compose:

docker-compose up --build




