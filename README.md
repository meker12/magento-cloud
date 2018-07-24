# Magento 2.2.5 Magento Commerce (Cloud)

This sample repository helps you deploy a Magento 2.2.5 Enterprise Edition (EE) instance in the cloud. You must be a licensed user of Magento Commerce (Cloud) to use the example in this repository.

This example is based on using the Composer to load dependencies and get the Magento vendor folders.

## Create an authorization file
To install and update the Magento software, you must have an `auth.json` file in your project's root directory. `auth.json` contains your Magento EE [authorization credentials](http://devdocs.magento.com/guides/v2.2/install-gde/prereq/connect-auth.html).

In some cases, your project might already have an `auth.json` file. Check to see if it exists and has your authentication credentials before you create one.

To create an `auth.json` file:

1.  Copy the provided sample using the following command:

        cp auth.json.sample auth.json
2.  Open the `auth.json`file in a text editor.
3.  Replace `<public-key>` and `<private-key>` with your authentication credentials.

    See the following example:

        "http-basic": {
           "repo.magento.com": {
              "username": "<public-key>",
              "password": "<private-key>"
            }
        }
3.  Save the updated file and exit the text editor.

## Repository structure
Here are the specific files for this example to work on Magento Commerce (Cloud):

```
.magento/
         /routes.yaml
         /services.yaml
.magento.app.yaml
auth.json
composer.json
magento-vars.php
php.ini
```

`.magento/routes.yaml` redirects `www` to the naked domain, and specifies that the application that will be serving HTTP is named `php`.

`.magento/services.yaml` sets up a MySQL instance, plus Redis and Solr. 

``composer.json`` fetches the Magento Enterprise Edition and some configuration scripts to prepare your application.

## Documentation
For more details, see our [Magento Commerce Cloud Guide](http://devdocs.magento.com/guides/v2.2/cloud/bk-cloud.html). 

