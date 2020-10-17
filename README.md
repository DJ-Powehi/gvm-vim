# New Golem Network - Light Bounty #1
## Compile VIM On Single Golem Node
*Your task is to build a VIM binary inside image running on top of the Golem Network and then run it on your native machine.*

## Requirements
- Python3 + Pip
- Docker + Compose + Machine + Virtualbox (MacOS case)
- gvmkit-build
- yapapi

## Obligatory Steps
- you’ve built a docker image that compiles VIM
- you’ve converted this image into a Golem VM image
- you’ve run it on devnet-alpha.2 network using our Python high-level API
- you’ve successfully run the compiled binary on your native machine

## Instructions
- install requirements
- create a virtualenv
- activate virtualenv
- install gvmkit-build and yapapi via pip
- build and tag the Dockerfile
- build and push the tagged image using gvmkit-build
- copy the generated hash link and paste it into IMAGE_HASH inside vim-gvm.py
- run yagna service in a standalone terminal
- on another terminal, initialize the yagna payment and wait for faucet and tx
- once the account is registered, create a requestor
- note the output key and export it as the YAGNA_APPKEY environment variable
- run vim-gvm.py
- wait a couple of minutes for VIM to compile into your machine
- turn the downloaded file into an executable via chmod
- open VIM :)

## Commands Used
- pip install -U gvmkit-build yapapi
- docker build -t vim:v1 .
- gvmkit-build vim:v1
- gvmkit-build vim:v1 --push
- yagna service run
- yagna payment init -r
- yagna app-key create requestor
- export YAGNA_APPKEY={requestor_output}
- python3 run.py
- chmod +x vim
- ./vim

## Thanks
- @thomgabriel for helping out during the process
- @iRhonin for the bootstrap code
- @golemfactory for pushing decentralization, OS and Python <3