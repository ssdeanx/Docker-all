# Master Docker (MCP) Server

## Overview

This project provides a versatile and powerful MCP server for managing various development tasks. It is designed to be extensible, modular, and easy to use, providing a single point of control for a variety of tools and technologies. The server is built using Node.js and is primarily designed to integrate with the roo-cline VS Code extension, but it can also be used as a standalone tool. It includes a robust Docker module, a CLI interface, a GET API, a scholarly data integration module, an authentication and authorization system, and a GraphQL endpoint.

## Features

*   **Docker Module:** Provides comprehensive tools for managing Docker containers and images, including:
    *   `dockerImageBuild`: Builds Docker images from Dockerfiles.
    *   `dockerImagePush`: Pushes Docker images to registries.
    *   `dockerImagePull`: Pulls Docker images from registries.
    *   `dockerImageDelete`: Deletes Docker images.
    *   `dockerContainerCreate`: Creates new Docker containers.
    *   `dockerContainerStart`: Starts Docker containers.
    *   `dockerContainerStop`: Stops Docker containers.
    *   `dockerContainerRestart`: Restarts Docker containers.
    *   `dockerContainerPause`: Pauses running Docker containers.
    *   `dockerContainerDelete`: Deletes Docker containers.
    *   `dockerContainerLogs`: Retrieves logs for a specified Docker container.
    *   `dockerResourceMonitor`: Monitors the CPU, memory, and network usage of a Docker container.
    *   `dockerEventMonitor`: Monitors Docker events, such as container creation, start, stop, and deletion.
    *   `dockerInspectContainer`: Retrieves detailed information about a Docker container.
    *   `setContainerResourceLimits`: Sets resource limits for a specific container.
    *   `getContainerResourceLimits`: Retrieves resource limits set on a specific container.
    *   `deployDockerSwarm`: Deploys a Docker container to a Docker Swarm cluster.
        *   `dockerComposeUp`: Creates and starts containers using a `docker-compose.yml` file.
        *   `dockerComposeDown`: Stops and removes containers defined in a `docker-compose.yml` file.
    *   `deployToKubernetes`: Deploys a Docker container to a Kubernetes cluster.
    *   `deployToAzureAppService`: Deploys a Docker container to Azure App Service.
    *   `deployToAzureVM`: Deploys a Docker container to an Azure Virtual Machine.
    *    `deployToGCloudVM`: Deploys a Docker container to a Google Cloud VM.
    *   **Advanced File Operations**
        *   `dockerFileMount`: Mounts a host directory into a container.
        *   `dockerFileExecute`: Executes a command within the context of a specific file in the container.
        *   `dockerFileExtract`: Extracts specific sections or lines from a file within a container.
        *   `dockerFileChecksum`: Calculates the checksum of a file within a container.
        *   `dockerFileStat`: Retrieves detailed information about a file within a container.
        *   `dockerFileCopyFromHost`: Copies a file from the host to a container.
        *  `dockerFileCopyToHost`: Copies a file from a container to the host.
        *  `dockerFileDiff`: Compares two files within a container or between a container and the host.
        *   `dockerFileSearch`: Searches for files within a container.
        *   `dockerFileSync`: Synchronizes files between a container and the host.
        *   `dockerFilePermissions`: Manages file permissions within a container.
        *   `dockerFileOwner`: Manages ownership of files within a container.
        *   `dockerVolumePrune`: Removes all unused local volumes.
        *   `dockerSystemDf`: Shows the amount of disk space used by the docker daemon.
        *   `dockerSystemPrune`: Removes all unused data.*   **CLI Module:** Provides a command-line interface for interacting with the MCP server, including:
    *   `serverStatus`: Checks if the MCP server is running and responsive.
    *   `listContainers`: Lists all Docker containers.
    *   `listImages`: Lists all Docker images.
    *   `listVolumes`: Lists all Docker volumes.
    *   `listKeys`: Lists all API keys and their associated permissions.
    *   `configGet`: Retrieves the current configuration of the MCP server.
    *   `configSet`: Sets or updates the configuration of the MCP server.
    *   `logs`: Retrieves the logs of the MCP server.
    *   `interactivePrompts`: Provides context-aware interactive prompts within the CLI.
    *   `commandAutoCompletion`: Provides auto-completion suggestions for commands and arguments.
    *   `outputFormatter`: Formats the output of CLI commands in various formats.
    *   `commandGenerator`: Automatically generates CLI commands based on the available modules.
    *   `commandValidator`: Validates CLI commands and arguments based on the current context.
    *   `interactiveHelpGenerator`: Dynamically generates help messages for CLI commands.

*   **GET Module:** Provides a RESTful API for retrieving data from the MCP server, including:
    *   `getServerStatus`: Retrieves the status of the MCP server.
    *   `listContainers`: Retrieves a list of all Docker containers.
    *   `listImages`: Retrieves a list of all Docker images.
    *   `listVolumes`: Retrieves a list of all Docker volumes.
    *   `getContainerLogs`: Retrieves logs for a specified Docker container.
    *   `getContainerStats`: Retrieves resource usage statistics for a specified Docker container.
    *   `listAPIKeys`: Retrieves a list of all API keys and their permissions.
    *   `getScholarlyArticles`: Retrieves a list of scholarly articles based on search criteria.
    *   `dataFormatter`: Formats the data returned by GET endpoints in various formats.
    *   `dataFilter`: Filters the data returned by GET endpoints based on query parameters.
    *   `dataSorter`: Sorts the data returned by GET endpoints based on query parameters.

*   **Scholarly Module:** Provides tools for accessing and processing scholarly data, including:
    *   `searchArticles`: Searches scholarly databases for articles.
    *   `getArticleMetadata`: Retrieves metadata for a specific article.
    *   `getRelatedArticles`: Finds articles related to a given article.
    *   `extractEntities`: Extracts entities from an article.
    *   `getArticleText`: Retrieves the full text of an article.
    *   `downloadArticle`: Downloads an article in a specified format.
    *   `trackCitations`: Tracks citations of a given article over time.
    *   `citationGenerator`: Automatically generates citations for scholarly articles.
    *   `keywordExtractor`: Extracts relevant keywords and keyphrases from scholarly articles.
    *   `summaryGenerator`: Generates concise summaries of scholarly articles.

*   **Authentication Module:** Provides tools for managing API keys and permissions, including:
    *   `generateAPIKey`: Generates a new API key with specified permissions.
    *   `verifyAPIKey`: Verifies an API key and its permissions.
    *   `getAPIKeyPermissions`: Retrieves the permissions associated with an API key.
    *   `addPermissions`: Adds new permissions to an existing API key.
    *   `removePermissions`: Removes specified permissions from an API key.
    *   `deleteAPIKey`: Deletes an API key.
    *  `permissionValidator`: Validates whether a given API key has the necessary permissions for a specific action.
    *   `apiKeyRotator`: Automatically rotates API keys on a regular schedule.
    *   `twoFactorAuthenticator`: Adds two-factor authentication (2FA) support.

*   **GraphQL Module:** Provides a GraphQL API for accessing and manipulating data from various sources, including:
    *   `dynamicSchemaGenerator`: Automatically generates a GraphQL schema based on the available data sources.
    *   `queryOptimizer`: Optimizes GraphQL queries for performance.
    *   `dataLoaderIntegration`: Integrates with DataLoader for efficient data fetching.
    *   `schemaDefinitionLanguage (SDL)`: Uses SDL to define the GraphQL schema.
    *   `resolverMap`: Defines resolvers for each field in the schema.
    *   `queryComplexity`: Calculates the complexity of a GraphQL query.
    *   `queryDepthLimiting`: Limits the depth of nested queries.
    *   `persistedQueries`: Stores and reuses frequently executed queries.
    *   `dataFetchingOptimization`: Optimizes data fetching in resolvers.
    *   `errorHandling`: Implements robust error handling in resolvers.
    *   `security`: Implements security measures for the GraphQL API.

## Technologies*   **Node.js:** [Node.js Website](https://nodejs.org/)
*   **Express.js:** [Express.js Website](https://expressjs.com/)
*   **Dockerode:** [Dockerode GitHub](https://github.com/apocas/dockerode)
*   **Commander.js:** [Commander.js GitHub](https://github.com/tj/commander.js)
*    **Bcrypt:** [Bcrypt GitHub](https://github.com/kelektiv/node.bcrypt.js)
*  **GraphQL:** [GraphQL Website](https://graphql.org/)
*   **Apollo Server Express:** [Apollo Server Express GitHub](https://github.com/apollographql/apollo-server)
*   **MCP Inspector:** [MCP Inspector GitHub](https://github.com/modelcontextprotocol/inspector)
*   **Azure SDK for Node.js:** [Azure SDK for Node.js Documentation](https://learn.microsoft.com/en-us/javascript/api/overview/?view=azure-node-latest)
*  **Google Cloud SDK for Node.js:** [Google Cloud SDK for Node.js Documentation](https://cloud.google.com/nodejs/docs/reference)
*   **Kubernetes SDK for Node.js:** [Kubernetes SDK for Node.js Documentation](https://kubernetes.io/docs/reference/using-api/client-libraries/#node-js-client)

## Usage

To use the MCP server, follow these steps:

1.  Clone the repository: `git clone [repository URL]`
2.  Install dependencies: `npm install`
3.  Configure the server: Modify the `config.js` file to set up API endpoints, database connections, and other settings.
4.  Start the server: `node server.js`

Once the server is running, you can interact with it using the CLI, the GET API, or the GraphQL endpoint.

## Contributing

We welcome contributions to this project! Please see our contributing guide for more details on how to get involved.

## License
This project is licensed under the MIT License.
