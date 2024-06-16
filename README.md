# APIs.io Artisanal
This is an APIs.io search node dedicated to being the inbox for the network. This where we will publish all new APIs that we find, to begin fleshing out and publishing to other network search nodes once they have an OpenAPI defining each API.

## APIs.io
[APIs.io](https://apis.io/) is a search engine that utilizes the APIs.json format to define each of the APIs present in the search index. To make the management of thousands of APIs easier, we have broken the search engine up into many individual search nodes, with this one being the gateway where all APIs begin, until they are distributed to a specific node.

## GitHub
APIs.io runs 95% on GitHub using [the api-search organization](https://github.com/api-search) in combination with the GitHub organizations for [APIs.json](https://github.com/apis-json) and [API Commons](https://github.com/api-commons/). GitHub provides the underlying repositories where we store code and content, but the websites also run using GitHub Pages which are the human facing aspect of each search node. GitHub allows us to run the search engine in an open source way that allows anyone to put to work and contribute.

## APIs.json
[APIs.json](https://apisjson.org/) is an open-source machine-readable format for describing the operations around private, partner, or public APIs, making them more easily discoverable by consumers. APIs.json provides a way to describe the API producer, but also individual APIs, and their documentation, pricing, and other human and machine-readable elements that API consumers will need to put them to work.

## Artisanal
This repository is where the work to build the index for APIs.io began, and continues to be where any new API is added to the search index. When you add an APIs.json through the form on APIs.io it adds the APIs.json here under [the _apis folder](https://github.com/apis-json/artisanal/tree/main/_apis). Anyone can add an API to the index using the APIs.io form, submitting a pull request on this repository, or simply by adding an issue to this repository with the name, description, and URL of the API. 

## Support
If you have any questions about this work or a specific API you can visit the [discussion forum for APIs.io](https://github.com/orgs/api-search/discussions), or you are welcome to submit an issue on this repository. If you have questions about APIs.json, we recommend [submitting an issue on the repository for the API specification](https://github.com/apis-json/api-json/issues).


