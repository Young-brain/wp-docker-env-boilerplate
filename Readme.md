# Docker Environment Boilerplate for WordPress

## Instructions
1. You need to add the string to `hosts` file your OS:  
`127.0.0.1 	wp-docker-boilerplate.local`
2. Run command `make env.create`, then fill the config data.   
2. Run command `make d.up`
3. Run command `make c.install` for installing dependencies and WordPress
4. Visit site [wp-docker-boilerplate.local](http://wp-docker-boilerplate.local)   

### Import/Export DB

#### Import  
You need to put on your file to `./docker/mysql/backup` with the name `import_db.sql`, then you need to run the command `make mysql.import`.

#### Export
You need to run the command `make mysql.export`, then you will see the exported file by `/docker/mysql/backup` path.

---
### Other cases
If you have a problems with access right for files, try using the next command for fixing it:

```
# It is using your user:usergroup
make fix-access-right-for FILE/DIR`
``` 
or  
`sudo chown USER:GROUP FILE`

If you want change domain, you need to change `server_name` in `./docker/nginxconf.d/default.conf`.


##  If you have troubles with VPN
1. If you use VPN, you need to disable VPN and run command:  
`docker network create localdev`
2. After It you can run your VPN.
3. Add the code at end of the file:
   ```networks:
    default:
     external:
      name: localdev
3. Make to  
 `docker-compose up -d`
 
 

