# Removing Docker Images and Volumes

[Source](https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)

The official command to remove all unused data (including volumes without containers) 


`docker system prune  `


If you want to limit to volumes alone, removing only unused volumes:

`docker volume prune`
