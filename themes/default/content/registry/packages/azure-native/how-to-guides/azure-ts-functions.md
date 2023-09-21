---
title: "Deploying Azure Functions | TypeScript"
h1: "Deploying Azure Functions"
linktitle: "Deploying Azure Functions"
meta_desc: "Deploying Azure Functions How-to Guide using TypeScript"
no_edit_this_page: true
cloud: azure
language: ts
layout: package
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/mktutorial. -->

<p class="mb-4 flex">
    <a class="flex flex-wrap items-center rounded-md font-display text-lg text-white bg-blue-600 border-2 border-blue-600 px-2 mr-2 whitespace-no-wrap hover:text-white" style="height: 45px;" href="https://github.com/pulumi/examples/tree/master/azure-ts-functions" target="_blank">
        <span><i class="fab fa-github pr-2"></i> View Code</span>
    </a>
    <a href="https://app.pulumi.com/new?template=https://github.com/pulumi/examples/blob/master/azure-ts-functions/README.md" target="_blank">
        <img src="https://get.pulumi.com/new/button.svg" alt="Deploy">
    </a>
</p>


Starting point for building serverless applications hosted in Azure Functions.

## Running the App

1.  Create a new stack:

    ```
    $ pulumi stack init dev
    ```

1.  Login to Azure CLI (you will be prompted to do this during deployment if you forget this step):

    ```
    $ az login
    ```

1.  Restore NPM dependencies:

    ```
    $ npm install
    ```
    
1. Set the Azure region location to use:
    
    ```
    $ pulumi config set azure-native:location westus2
    ```

1.  Run `pulumi up` to preview and deploy changes:

    ```
    $ pulumi up
    Previewing changes:
    ...

    Performing changes:
    ...
    Resources:
        + 8 created

    Duration: 1m18s
    ```

1.  Check the deployed endpoint:

    ```
    $ pulumi stack output endpoint
    https://appg-fsprfojnnlr.azurewebsites.net/api/HelloNode?name=Pulumi
    $ curl "$(pulumi stack output endpoint)"
    Hello from Node.js, Pulumi
    ```
