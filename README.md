### Run docker compose up
```bash
docker-compose up -d
```
### Create database schema
```bash
docker exec -it mysql -c 'cat /schema/*.sql | mysql -u root -p --password=guacamole guacamole_db'
```
### Restart containers
```bash
docker compose restart
```
### Access guacamole web interface
http://localhost:8080/guacamole/
