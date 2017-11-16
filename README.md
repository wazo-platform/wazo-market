# wazo-market
Content of the Wazo market place

# Create your own market for dev

### Create custom configuration file in your wazo server.

````
cat <<EOF > /etc/wazo-plugind/conf.d/010-market-dev.yml
market:
  host: 172.17.0.1
  port: 8888
EOF
````

By default the `0.1` folder will be use. it's the version of the market.

If you want to create a new plugins version

````
mkdir /path/to/wazo-market/dev
touch /path/to/wazo-market/dev/plugins
````

add key version into your custom configuration file: 

/etc/wazo-plugind/conf.d/010-market-dev.yml
````
market:
  host: 172.17.0.1
  port: 8888
  version: dev
````

### Launch container on your host

````
docker run -p 8888:80 -v /path/to/wazo-market:/usr/share/nginx/html \
    --name wazo-market-dev -d nginx
````