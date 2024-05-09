# Opencart v2 Demo

This project is a study and research project focused on Opencart version 2.3.0.2. The goal of this project is to explore the features and functionality of Opencart v2 and gain a deeper understanding of its capabilities.

# Opencart v2 Demo

This project is a study and research project focused on Opencart version 2.3.0.2. The goal of this project is to explore the features and functionality of Opencart v2 and gain a deeper understanding of its capabilities.

## Setup with Docker

This project can be set up using Docker and Docker Compose. Here are the steps to get it up and running:

1. **Build and run the Docker containers**

    Run the following command in the root directory of the project:

    ```bash
    docker-compose up -d
    ```

    This command will build the Docker images if they haven't been built already, and start the containers.

2. **Access the application**

    Open your web browser and navigate to `http://localhost/install/index.php` to start the OpenCart installation process.

    Use the following database connection details:

    - Database host: `db`
    - Username: `root`
    - Password: `root`
    - Database name: `opencart`

3. **Stop the Docker containers**

    When you're done, you can stop the Docker containers by running the following command in the root directory of the project:

    ```bash
    docker-compose down
    ```

Please note that this setup is intended for development and testing purposes only, and may not be suitable for production use.