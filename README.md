# mealtime-platform

This is the main (parent) repo. It builds and runs containers for Backend (Rails API), PostgreSQL and Frontend (React) using docker-compose.

## Setup

1. Install *docker* and *docker-compose*

    Make sure that daemon is running and available

2. Build Images

   **Linux**:

   ```sh
   docker-compose build
   ```
   or
   ```sh
   docker-compose up --build
   ```

3. Setup db

    ```sh
    docker-compose exec backend rake db:setup
    ```

    NOTE: you'll have to re-run

    ```sh
    docker-compose exec backend rake db:migrate
    ```

    whenever there are new migrations.

4. Start server or run commands (for example tests)

    ```sh
    docker-compose up
    ```

    ```sh
    docker-compose run backend COMMAND
    ```

    you can also pass environment through `-e` parameter

    ```sh
    docker-compose run -e "RAILS_ENV=production" backend COMMAND
    ```
