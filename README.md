# Client server project
In this project, multiple clients can request for information/files and the server fulfills that request.

Server has two copies called mirror 1 (port 8090) and mirror 2 (port 8091), which are executed simultaneously with server. 

The purpose of mirrors is to do load balancing in following manner:

First three connections will be handled by server, next three by mirror 1, next three by mirror 2 and then in an alternating manner between server, mirror 1 and mirror 2.

For each request by a client, server will look in ~ directory by default.

Compile and run server and mirrors beforehand: ./server _port_, ./mirror1 8090, ./mirror2 8091 followed by client: ./client _IP_address_ _port_

(Use _hostname -i_ to get server IP for client connection)

Usage (Client commands):

**dirlist -a** : returns list of folders under home directory in alphabetical order

**dirlist -t** : returns list of folders under home directory in the order in which they were created

**w24fn _filename_** : returns filename, size (in bytes), date created and file permissions (first occurence if same file in multiple folders)

**w24fz _size1_ _size2_** : return an archive temp.tar.gz that contains all the files in home directory whose file-size >= _size1_ and <= _size2_

**w24ft _extension list_** : return an archive temp.tar.gz that contains all the files in home directory belonging to the type/s listed in extension list

**w24fdb _date_** : return an archive temp.tar.gz that contains all the files in home directory whose creation date <= _date_

**w24fda _date_** : return an archive temp.tar.gz that contains all the files in home directory whose creation date >= _date_

**quitc** : client process is terminated
