# Strapi (Opensource Headless CMS) App for Gatsby 3 pet-project

Back-end for [Gatsby v3 App](https://github.com/WebDevelopUa/gatsby_02)

-------

Requirements:

- [Node.js](https://nodejs.org/uk/)

### Run in terminal

``` 
npm i
npm run develop
```

### Check the result:

- [localhost:1337/admin/auth/register-admin](http://localhost:1337/admin/auth/register-admin)
- [localhost:1337/admin](http://localhost:1337/admin)

**Credentials** for the [DB](./tmp/data.db):

- admin@admin.com
- Admin2000

## Content Type

gives structure for app data

* Content-Types Builder => Create new collection type => 'JOB-section':
  - text field => 'COMPANY' => Advanced settings => Required field (check)
  - text field => 'POSITION' => Advanced settings => Required field (check)
  - text field => 'DATE' => Advanced settings => Required field (check)
  - add another field => component => use an existing component => select a component => 'JOB-description' => Finish

* Content-Types Builder => Create new component => 'JOB-description':
  - text field => 'NAME' => Advanced settings => Required field (check) => Finish => Save

## Content

adding app data

* Collection Types => 'JOB-section' => Add New JOB-sections:
  - create an entry => fill the fields => Finish => Save => Publish
  - check the result [localhost:1337/JOB-sections](http://localhost:1337/JOB-sections)
    => ```{"statusCode":403,"error":"Forbidden","message":"Forbidden"}```
  - Settings => [Roles & Permissions](http://localhost:1337/admin/settings/users-permissions/roles)
    => [Public](http://localhost:1337/admin/settings/users-permissions/roles/2) => check ```find, findone ``` fields =>
    Save
  - check the result [localhost:1337/JOB-sections](http://localhost:1337/JOB-sections)
    => ``` [{"id":1,"company":"Praesent mollis augue","position":"Integer accumsan augue eu nisl ultrices tempor","date":"10/10/2010","published_at":"2021-05-04T08:28:59.144Z","created_at":"2021-05-04T08:27:56.349Z","updated_at":"2021-05-04T08:28:59.211Z","description":[{"id":1,"name":"There is no one who loves pain itself, who seeks after it and wants to have it, simply because it is pain..."},{"id":2,"name":"Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit..."},{"id":3,"name":"Proin varius dui sed nulla dignissim porta ut et elit. Praesent id erat sit amet eros malesuada laoreet a non velit."}]}]```

## Content storage:

connect the DB to see the tables

``` 
jdbc:sqlite:****\.tmp\data.db

DBMS: SQLite (ver. 3.34.0)
Case sensitivity: plain=mixed, delimited=mixed
Driver: SQLite JDBC (ver. 3.34.0, JDBC2.1)
Ping: 78 ms
```

``` 
// config/database.js

module.exports = ({ env }) => ({
  defaultConnection: 'default',
  connections: {
    default: {
      connector: 'bookshelf',
      settings: {
        client: 'sqlite',
        filename: env('DATABASE_FILENAME', '.tmp/data.db'),
      },
      options: {
        useNullAsDefault: true,
      },
    },
  },
});

```

-----
-----

# Kick back & Relax

-----
-----

- [Strapi Quick Start Guide](https://strapi.io/documentation/developer-docs/latest/getting-started/quick-start.html#_1-install-strapi-and-create-a-new-project)
- [gatsby-source-strapi](https://www.npmjs.com/package/gatsby-source-strapi)
- [Getting Started with Gatsby](https://strapi.io/documentation/developer-docs/latest/developer-resources/content-api/integrations/gatsby.html#create-a-gatsby-app)
- [Deployment](https://strapi.io/documentation/developer-docs/latest/setup-deployment-guides/deployment.html)
  on [Heroku](https://strapi.io/documentation/developer-docs/latest/setup-deployment-guides/deployment/hosting-guides/heroku.html)

``` 
TIP

When you use --quickstart to create a Strapi project locally, 
a SQLite database is used which is not compatible with Heroku. 
Therefore, another database option must be chosen.
```

``` 
WARNING

For security reasons, the Content Type Builder plugin is disabled in production. 
To update content structure, please make your changes locally and deploy again.

Additionally, if you wanted to change the default production mode in Heroku, 
it wouldn't work as the file system is temporary. 
Strapi writes files to the server when you update the content-types 
and these updates would disappear when Heroku restarts the server.

Therefore, modifications that require writing to model creation or other json files, 
e.g. creating or changing content-types, require that you make those changes 
on your dev environment and then push the changes to Heroku.
```

- [Deployment on Qovery](https://strapi.io/documentation/developer-docs/latest/setup-deployment-guides/deployment/hosting-guides/qovery.html#deploying-with-the-web-interface)

