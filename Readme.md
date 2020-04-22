# NGINX Packer

## Prerequisites

- Git
- Packer
- Chef
- Vagrant


## What is Packer?

**Packer** is a FOSS (*Free Open Source Software*) tool maintained by the community to be used to create programmed images of machines. This works through a single JSON (Javascript Object Notation) file that tells Packer how to configure itself. The primary purpose of a Packer file is to interact with a cloud service such as **Microsoft Azure**, or **Amazon Web Services**, so that a network engineer or DevOps can create a large number of systems all with the same tools and software installed, mitigating a major cause of "It works on my machine".

A Machine Image is a static, pre-configured operating system, with all the tools and software that a company might require for their CI/CD pipeline, which can then be moved on to platforms such as **EC2**. 

## Installation and running

To download this repo, please run: `git clone git@github.com:AshIsbitt/NodePacker.git`

Note that to continue, you may need to edit lines 10, 12 and 13 of `packer.json` to your local SSH key and AWS Subnet. 

You will then need to run `berks vendor` to pull the required Chef cookbooks from Github.

To validate that this was successful, please run `packer validate packer.json`. If an error occurs here, you may need to delete the `berks-cookbooks` folder and run `berks vendor` again.

Lastly, run `packer build packer.json`