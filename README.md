Instana Agent Static Docker
===========================

This build of the Instana agent includes all sensors. It requires proxy settings only for egress access to the ${INSTANA_AGENT_ENDPOINT}, which may either be for your self hosted Instana installation or for the Instana SaaS.

Building
========

docker build ./ --build-arg FTP_PROXY=${INSTANA_AGENT_KEY} --no-cache

*Note*

FTP_PROXY is being abused to pass in the agent key for the package download during docker build, we are doing this until docker build time secrets issue is resolved: [issue GH33343](https://github.com/moby/moby/issues/33343)

Download Static Agent
==========

The static image can be found on containers.instana.io and can be downloaded using the following commands:

docker login containrs.instana.io -u _ -p <agent_key>
docker pull containers.instana.io/instana/release/agent-static:latest
