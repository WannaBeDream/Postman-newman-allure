# Postman + newman + github actions + allure (Simple store template)

## Commands Overview
1. Run `npm i`  to install node.js dependencies.
2. Run `npm run tern-on-api` to run testing server locally on 3000 port.
3. Run `npm run test` to run newman runner with `store.collection.json` through API on local server.
4. Run `allure:report` to run generate the static report web-application folder.
5. Run `allure:clear` to clean up current folder.
6. Run `report` to run generate the static report web-application folder and serve the report locally without prior installation.

### REST API Overview
Routes `/products`, `/orders` and `/users`. Below is a table of supported operations with `products` as example resource. The same operations are also supports for `orders/` and `users/`.

| VERB     |Route          | Input      | Output             |
|----------|---------------|------------|--------------------|
| GET      | /products     | *None*     | **Array**          |
| GET      | /products/:id |  **e.g 3** | **Object**         |
| POST     | /products     | **object** | **Created object** |
| PUT      | /products     | **object** | **Updated object** |
| DELETE   | /products/:id | **e.g 3**  | **Deleted object** |

Test examples overview:
- Test pagination, by way like `http://localhost:3000/users?page=1&pageSize=2`. 
- Test sorting, by way like `http://localhost:3000/users?sortOrder=ASC&sortKey=firstName`. You can sort an any resource response using query parameters sortOrder and sortKey.
-  Test status code for REST API (200,400 and so on).
-  Test response time.
-  Test response thanks to json schema validation.

### Useful links
Doc for json schema validation, to check output API response (only take a look once, no need to learn this doc) 
- <a href="https://json-schema.org"> json schema docs </a>
- <a href="https://openapi.tools"> openapi tools </a>
- <a href="https://github.com/WannaBeDream/openapi-directory"> openapi directory </a>
- <a href="https://github.com/WannaBeDream/openapi-boilerplate"> openapi boilerplate </a>
- <a href="https://github.com/WannaBeDream/openapi-gui"> openapi gui </a>
