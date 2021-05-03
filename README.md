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

## Content Type

gives structure for app data

* Content-Types Builder => Create new collection type => 'JOB-section':
  - text field => 'COMPANY' => Advanced settings => Required field (check)
  - text field => 'POSITION' => Advanced settings => Required field (check)
  - text field => 'DATE' => Advanced settings => Required field (check)
  - add another field => component => use an existing component => select a component => 'JOB-description' => Finish

* Content-Types Builder => Create new component => 'JOB-description':
  - text field => 'NAME' => Finish => Save

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

