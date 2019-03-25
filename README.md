**Lumen with docker and mysql**

**Installation steps:** 

1. Clone repository:

    ```
    $ git clone https://github.com/gilglecio/lumen-docker-mysql.git lumen
    ```

2. Create two new textfiles named `db_root_password` and `db_password` and place your preferred database passwords inside:

    ```
    $ echo "myrootpass" > db_root_password
    $ echo "myuserpass" > db_password
    ```

3. Open a new terminal/CMD, navigate to this repository root (where `docker-compose.yml` exists) and execute the following command:

    ```
    $ docker-compose up -d
    ```

    This will download/build all the required images and start the stack containers. It usually takes a bit of time, so grab a cup of coffee.

4. After the whole stack is up, enter the app container and install the framework of your choice:

    ```
    $ docker exec -it app bash
    $ nano .env
    $ php artisan migrate --seed
    ```

5. That's it! Navigate to `http://localhost:4004` to access the application.