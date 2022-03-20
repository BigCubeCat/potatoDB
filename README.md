# [<img src="kivi.png" width="64"/>](kivi.png) KiViDB
🥝**KiviDB** is simple key-value database written in Golang.
## Installation
1. **Build** project:
```sh
go build .
```
2. Create **.env** file like this:
```env
DIR_NAME=YOUR_DB_NAME
ADDRESS=8080
LOG_FILE=kividb.log
HOST=localhost
```
3. Run ```./kiviDB```
4. Setup and work with database by http API.

## Routes
> /cluster/
> /doc/

## Request
### **/doc** (for single-document operations):
#### Get document by id in cluster
> GET:
>```
> http://localhost:8080/doc/cluster_name/id
>```
#### Create new value in cluster with autogenerated-key:
> POST:
> ```
> http://localhost:8080/doc/cluster_name
>```
>JSON example:
>```json
>{
>    "Value": "SomeValue"
>}
>```
#### Create new value in cluster with known-key:
> POST:
>```
> http://localhost:8080/doc/cluster_name/id
>```
>JSON example:
>```json
>{
>    "Value": "SomeValue"
>}
>```
#### Delete value by id (in cluster, of course):
> DELETE:
>```
> http://localhost:8080/doc/cluster_name/id
>```
### **/cluster** (for create and delete cluster):
### Create cluster:
> POST:
>```
> http://localhost:8080/cluster/cluster_name
>```
#### Get all documents in cluster:
> GET:
>```
> http://localhost:8080/cluster/cluster_name
>```
#### Delete cluster (***warning! it also delete all documents in cluster!***):
> DELETE:
>```
> http://localhost:8080/cluster/cluster_name
>```
