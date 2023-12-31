# Compliance-Framework Infrastructure Example

This project helps setting up infrastructure for both local development and (soon) cloud development on kubernetes.

It could be considered an example deployment as opposed to actually part of the working code.

There are three main components that it checks out and sets-up:

- Portal: this is the Frontend GUI.
- Configuration Service: This acts as the API and is the "brain".
- Assessment Runtime: This is what interacts with the cloud providers and gathers information in order to report back to configuration service.

In a real world deployment of CF, teams would likely write their own version of this repo and deploy it to whatever infrastructure they preferred to work with as opposed to just using docker-compose.

Once the quickstart has been followed, there will be:

- A running instance of CF using docker-compose and scanning on an Azure subscription (this must be setup externally)
- The correct repos checked out as subdirectories ready to develop on.

# Quickstart

1. Make sure you have a docker-compatible socket environment set up with a functioning CLI, in addition, docker-compose.
1. Make sure azure client variables are set **(NOTE _this example project uses Azure_ but CF is not Azure specific)**:

```zsh
export AZURE_CLIENT_ID="[REPLACEME]"
export AZURE_CLIENT_SECRET="[REPLACEME]"
export AZURE_TENANT_ID="[REPLACEME]"
```

2. `make up` to checkout/update repos, build all the containers and spin them up
3. `make setup` should populate the data
