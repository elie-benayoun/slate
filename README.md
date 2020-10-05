# Slate Documentation

This API documenetation is based on slate , It allow to build designed documenttion from a markdown file

## How It Works 

All the markdown text is in the file located at *source/index.html.md* , simply ;odify it like you want 
> Remember that all the part that are in '''``` .... ```''' will be passed to the right side of the screen ( the code part)
  
If you want to pass text to this part simply add > before the text

## Prepare the documantaion for Deployement

To deploy the slate documentaion you will have to compile it in a build file , at this moment the documenation is already hosted hosted on firebase , so you will just have to compile it using the package called Middleman , The easiest way to do that is to use Docker  
Install Docker on your computer go into the terminal in the cloned file from github and symply runs the following lines  

This command is run only one time on a computer , once you run it you will not have to run it again if you want to deploy changes , run just the two other commands  
This command is building the docker image for slate and instaling all the dependencies 
```
docker build . -t slate
```  
  

The next command is creating the docker container  
* On OSX
```
docker run -d --rm --name slate -p 4567:4567 -v $(pwd)/build:/srv/slate/build -v $(pwd)/source:/srv/slate/source slate
```  


* On Windows
```
docker run -d --rm --name slate -p 4567:4567 -v ${pwd}/build:/srv/slate/build -v ${pwd}/source:/srv/slate/source slate
```  


Finally this command is creating the build file (or updating it)
```
docker exec -it slate /bin/bash -c "bundle exec middleman build"
```

You can now stop the docker container with this command
```
docker stop slate
```

## Deployement

To deploy on firebase , simply run
```firebase
firebase deploy
```

If you want to associate this documentation with another project don't forget to put the public folder as build and to not rewrite index.htnl

