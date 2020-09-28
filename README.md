# Execution Environment Image Hosting

Clone this repository, download Ansible-Runner, then run:

```
ansible-builder build -f input/execution-environment.yml --container-runtime=docker -c build_context --tag quay.io/beeankha/ee_image:latest
```

Then attempting to put on build trigger with:

https://quay.io/repository/beeankha/ee_image

### Rebuilding

Say you do not have `ansible-builder` installed, nor do you want it, and you just want to build an image from what is here.

```
docker build --rm=true -f build_context/Dockerfile --build-arg TAG=2.9 -t quay.io/beeankha/ee_image:2.9 build_context
```

This will build a version with Ansible 2.9.

**Note:** If you are running this with your own custom execution environment image, you will want to substitute your own quay.io account for beeankha.

