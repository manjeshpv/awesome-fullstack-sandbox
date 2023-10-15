# Awesome Fullstack Sandbox - Test Caprover

Test environment is immuatable and automated

## Setting up docker builds

### Docker Registry
- Signup to docker hub
- Enable privacy to private if push private images
- Visit caprover cluster menu and update docker registry with disable push

### Github actions
- Enable github actions
- add build-docker.yml file
- implement verion bump logic
- Enable write permission to github action
- Push the docker image to registry and send slack notification

# Deployment Manifest File
- Keep a `deployment-manifest.json` in monorepo to track the deployed images
- Create caprover automation using [caprover-cli](https://www.npmjs.com/package/caprover)
