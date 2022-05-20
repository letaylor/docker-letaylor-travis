
# docker-letaylor

This repo contains Docker images that are automatically built using Travis CI. It is not designed to scale to many images as each image is updated if any one image changes.

# Automatically push images to Docker Hub using Travis CI

## 1. Edit config files

Edit the following files:
* `.travis.yml` : alter `$IMAGE_NAME`.

## 2. Give Travis CI access to upload to Docker Hub

Store both `$DOCKER_PASSWORD` and `$DOCKER_USERNAME` securely in on Travis CI. These are used for authentication.

1. Login to the account you want Travis to use to upload on [hub.docker.com](https://hub.docker.com/).
2. Click on your username on the top left and go to 'Account Settings'.
3. On the left hand panel, go to 'Security' and enter your password as requested.
4. Now we'll create an API token. Name it Travis CI.
5. Create the token and copy it.
6. Login to your account on [travis-ci.org](https://travis-ci.org) and go to the repository that you want to add this automatic functionality to.
7. On the right next to 'More options' go to 'Settings' in the hamburger menu.
8. Add an environment variable with the name `DOCKER_PASSWORD` and give it the value of the API token that you copied from [hub.docker.com](https://hub.docker.com/).
9. Add an environment variable with the name `DOCKER_USERNAME` and give it your [hub.docker.com](https://hub.docker.com/) user name.
