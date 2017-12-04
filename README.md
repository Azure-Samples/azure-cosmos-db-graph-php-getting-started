---
services: cosmos-db
platforms: python
author: luisbosquez
---

# Developing a PHP Gremlin app using Azure Cosmos DB
Azure Cosmos DB is a globally distributed multi-model database. One of the supported APIs is the Graph (Gremlin) API, which provides a graph data model with [Gremlin query/traversals](https://tinkerpop.apache.org/gremlin.html). This sample shows you how to use the Azure Cosmos DB with the Graph API to store and access data from a PHP application.

## Running this sample

* Before you can run this sample, you must have the following prerequisites:

   * An active Azure account. If you don't have one, you can sign up for a [free account](https://azure.microsoft.com/free/). Alternatively, you can use the [Azure Cosmos DB Emulator](https://azure.microsoft.com/documentation/articles/documentdb-nosql-local-emulator) for this tutorial.
   * PHP 5.6+
   * composer (https://getcomposer.org/doc/00-intro.md)

* Then, clone this repository using `git clone https://github.com/Azure-Samples/azure-cosmos-db-graph-php-getting-started.git`

* Next, substitute the endpoint and authorization key in the `connect.php`, on line 8, with your Cosmos DB account's values:

```php
$db = new Connection([
    'host' => 'your_server_address',
    'username' => '/dbs/<db>/colls/<coll>',
    'password' => 'your_primary_key'
    ,'port' => '443'

    // Required parameter
    ,'ssl' => TRUE
]);
```

| Setting | Suggested Value | Description |
| ------- | --------------- | ----------- |
| your_server_address   | [***.graphs.azure.com] | This is the Gremlin URI value on the Overview page of the Azure portal, in square brackets, with the trailing :443/ removed.  This value can also be retrieved from the Keys tab, using the URI value by removing https://, changing documents to graphs, and removing the trailing :443/. |
| port | 443 | Set the port to 443 |
| username | `/dbs/<db>/colls/<coll>` | The resource of the form `/dbs/<db>/colls/<coll>` where `<db>` is your database name and `<coll>` is your collection name. |
| password | Your primary key | This is your primary key, which you can retrieve from the Keys page of the Azure portal, in the Primary Key box. Use the copy button on the left side of the box to copy the value. |

* From a command prompt or shell, run `composer install` from the top-level directory, where the `composer.json` file is, to get and resolve dependencies.

* From a command prompt or shell, run `php connect.php` to run the application.

## About the code
The code included in this sample is intended to get you quickly started with a PHP application that connects to Azure Cosmos DB with the Graph (Gremlin) API.

## More information

- [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction)
- [Azure Cosmos DB : Graph API](https://docs.microsoft.com/en-us/azure/cosmos-db/graph-introduction)
- [Gremlin PHP](https://github.com/PommeVerte/gremlin-php)
