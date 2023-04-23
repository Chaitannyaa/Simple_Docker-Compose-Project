Voting App
This is a simple web application for voting on your favorite programming language. The app is built with Flask and uses MySQL as the database.

Requirements
Docker
Docker Compose

How to use
Clone this repository to your local machine:

bash
Copy code
git clone https://github.com/yourusername/voting-app.git
Navigate to the project directory:

bash
Copy code
cd voting-app
Build and start the app with Docker Compose:

bash
Copy code
docker-compose up
Wait for the containers to start up and for the MySQL database to be initialized. This may take a few seconds.

Once the app is running, open a web browser and go to http://localhost:5000 to access the voting form.

Configuration
The following environment variables can be set to configure the app:

DB_USER - The username for the MySQL database (default is root)
DB_ROOT_PASSWORD - The password for the MySQL root user (default is password)
DB_DATABASE - The name of the MySQL database to use (default is votes)
DB_HOST - The hostname of the MySQL container (default is mysql-container)

These environment variables can be set in the environment section of the docker-compose.yml file, or passed in at runtime using the -e option with docker-compose.

License
This project is licensed under the MIT License - see the LICENSE file for details.







