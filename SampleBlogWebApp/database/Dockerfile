# using vNext image
FROM microsoft/mssql-server-windows-express
 
# create directory within SQL container for database files
RUN powershell -Command (mkdir C:\\SQLServer)
 
#copy the database files from host to container
COPY Blogging.mdf C:\\SQLServer
COPY Blogging_log.ldf C:\\SQLServer
 
# set environment variables
ENV SQLSERVER_SA_PASSWORD=Testing11@@
 
ENV ACCEPT_EULA=Y
 
ENV attach_dbs="[{'dbName':'Blogging','dbFiles':['C:\\SQLServer\\Blogging.mdf','C:\\SQLServer\\Blogging_log.ldf']}]"
