### Concept: 
The concept of docker file is simple the stucture should follow
- ```Image```: Blueprint of the container in simple word what run inside 
- ```container```: What run inside
- ```Dockerfile```: Script for building the image 
- ```Stages```: Can have multiple Stages
- ```Layers```: Each Dockerfile command adds a layer (cached to optimize builds).

The Dockerfile should on the root of the folder 

The step inside 
- Build 
  FROM {image} as builder -- for build the app
  WORKDIR /app -- for specify where is apply
  COPY /{File of reference} -- for the file to be paste  
