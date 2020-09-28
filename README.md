# Execution Environment Image Hosting

Clone this repository, download Ansible-Runner, then run:

```
ansible-builder build -f exec_env_image_example/execution-environment.yml --container-runtime=docker -c build_context --tag quay.io/beeankha/ee_image:latest
```

Then attempt to put on a build trigger with:

https://quay.io/repository/beeankha/ee_image

### Rebuilding

If you don't have `ansible-builder` installed (and you don't want to install it) and you just want to build an image from what is here, then run:

```
docker build --rm=true -f build_context/Dockerfile --build-arg TAG=2.9 -t quay.io/beeankha/ee_image:2.9 build_context
```

This will build a version with Ansible 2.9.

> **Note:** If you are running this with your own custom execution environment image, you will want to substitute your own quay.io account for `beeankha`.

