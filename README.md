# lumen-api!


## micro-service php api

>Lets get your local dependencies setup on your machine
PHP: Make sure PHP is installed on your machine. PHP >= 7.0. Furthermore, ensure that the following PHP extensions are installed. OpenSSL, PDO and Mbstring.
Composer: Navigate to the composer website and install it on your machine. Composer is needed to install Lumen's dependencies.

You'll also need familiarity with database concepts, and working knowledge of PHP.

----------
Get [Lumen](https://lumen.laravel.com/) globally on your machine.
>The stunningly fast micro-framework from Laravel - The PHP Framework For Web Artisans. Lumen is a subset lightweight part that has been stripped down for micro-service API development

    composer global require "laravel/lumen-installer"

>Use Git or checkout with SVN using the web URL.

       git clone https://github.com/p5150j/lumen-api.git
----------
    cd   lumen-api     
----------

    composer install
----------

    php artisan migrate
----------

    php -S localhost:8000 -t public

# Endpoints

| verb | uri |
|--|--|
|GET  | /api/authors/ |
|GET  | /api/authors/:id |
| POST | /api/authors/ |
| PUT | /api/authors/:id |
| DELETE | /api/authors/:id |

## Json objects are direct relations to tables in your db
    {
        "id": ,
        "name": "",
        "email": "",
        "github": "",
        "twitter": "",
        "location": "",
        "latest_article_published": "",
        "created_at": "",
        "updated_at": ""
    }

Need an `ORM` for more robust `joins` and `relationships`? Use [Eloquent](https://laravel.com/docs/5.6/eloquent) it comes connected out of the box, you will just need to un-comment the lines in your `app.php`

    $app->withFacades();
    $app->withEloquent();


`CORS` issues you may say? NP, add middleware for that

    $app->middleware([ 'Vluzrmos\LumenCors\CorsMiddleware']);
