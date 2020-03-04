## About package

`docker-lamp-start` is Docker environment configuration file structure that is best when used as submodule for your project. 
Usually, when we work on project we clone some repository and then there is need for setting Docker container within project. 
Installing this package as submodule, everything is in place and we can just change some values in environmental file.
This package is meant to cover basic PHP MySQL environement for web applications.
It will work in a way where publicly exposed location is `./public` (such can be found in most frameworks today).
If this is not case with your application structure (if you use something else than public directory for publicly exposed root), you should make some modification related to Apache configuration in Dockerfile.
Also, it's PHP image comes with xdebug configuration prepared (check Dockerfile)

## Simple Usage

1. from root of your project clone submodule in already initialized git project

    `git sumbodule add git@github.com:Tpojka/docker-lamp-start.git submodule/`

    // if you want to place it in another place in project, you should fix relative path in docker-compose.yml file in services:web:volumes section

2. build containers

    `docker-compose -f submodule/docker-lamp-start/docker-compose.yml -d`


    // executed from root location, docker-compose should be righteous pointed to docker-compose.yml file using -f flag

3. By default web container is conveniently named and you can acces it by

    `docker exec -it web-container /bin/bash`
    
4. Access location for browsers and clients is `http://localhost:8101`

5. You are good to go
    

## License

Package is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT). License file is distributed within this repository.
