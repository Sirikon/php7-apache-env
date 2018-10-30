# PHP7 Apache Env

Always copy everything to a new repository, use this as a boilerplate.

## Requirements

 - Docker
 - docker-compose

## Using with Bolt.cm

1. Download latest version of Bolt.cm [here](https://bolt.cm/distribution/bolt-latest.zip) (As today, it's 3.6.0).
2. Unzip inside `src` folder.
3. Rename:
    - `.bolt.yml.dist` -> `.bolt.yml`
    - `composer.json.dist` -> `composer.json`
    - `composer.lock.dist` -> `composer.lock`
    - `src/Site/CustomisationExtension.php.dist` -> `src/Site/CustomisationExtension.php`
4. Inside `src`, run the following commands:
    ```bash
    chmod -R 777 app/cache/ app/config/ app/database/ extensions/
    chmod -R 777 public/thumbs/ public/extensions/ public/files/ public/theme/
    ```
5. In the root folder, run `docker-compose up -d`. **Take note**: This will build the custom image the first time. Consequent times, if you modify the image inside `custom-php`, you'll need to run `docker-compose build` before `docker-compose up -d`.
6. Visit [localhost:8000](http://localhost:8000) and you should get the Bolt first user registration form.

## License

MIT
