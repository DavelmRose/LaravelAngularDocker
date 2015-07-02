# LaravelAngularDocker

## Laravel specific Docker set-up. 

### Getting started

#### Requirements 
Make sure you have a CoreOS VM or on OSX boot2docker installed and running. Also make sure you have docker-compose installed. 

1. docker-compose build
2. docker-compose up
3. cp -r www/api/.env.example www/api/.env
4. docker-compose run webserver bash -c "cd api && php artisan migrate && composer update"

Set up your vhosts:

```
# Test Project
192.168.59.103 api.test.com
192.168.59.103 admin.test.com
192.168.59.103 frontend.test.com
```

### Bonus shit

I've written a small nodejs wrapper for executing Laravel commands within the webserver container. Simply run ```sudo npm install -g```. Now run ```laradock -C webserver -c php artisan migrate```. Currently the response from Docker doesn't output, I'll fix that at some point. 

Visit http://ewanvalentine.io/running-laravel-and-angularjs-on-docker/ for more info. 
