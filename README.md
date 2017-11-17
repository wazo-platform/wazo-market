# wazo-market
Content of the Wazo market place

# Create your own market for dev

### Create custom configuration file in your wazo server.

* create `/etc/wazo-plugind/conf.d/010-market-dev.yml`
  ````
  market:
    host: 172.17.0.1  # host on which the docker will run
    port: 8888
    version: dev  # if you want another version than the default 0.1
  ````

* restart wazo-plugind: `systemctl restart wazo-plugind.service`

### (Optional) Create custom market version

* `mkdir /path/to/wazo-market/dev`
* `touch /path/to/wazo-market/dev/plugins`

### Launch container on your host

````
docker run -p 8888:80 -v /path/to/wazo-market:/usr/share/nginx/html \
    --name wazo-market-dev -d nginx
````
