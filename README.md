# UK D8 Dev Container

This is a full Drupal development environment based on docker. It's intended to make it easy to develop a single site that uses the UK Drupal 8 Installation Profile, or to develop the installation profile itself.

**Note:** By default, the docker containers in this project will map your host system `~/.ssh` directory, giving them access to your user's ssh keys. These containers are meant for local development only, and should not be pushed to another system unless this mapping is disabled. This configuration can be modified in the project's `docker-compose.yml` file if desired.

## Managing files using VS Code Remote Containers
For best performance, you can manage your code within a docker volume, and use VS Code to browse your workspace files. Your workspace files will not be available from your host operating system.

This setup requires:
* Docker Desktop 2.0+ (for macOS or Windows 10 Pro/Enterprise)
* VS Code
* VS Code Remote - Containers extension

*Optional Step: SQL dump import*
If you wish to start with an existing SQL database, you can do so by importing a SQL dump into the MySQL docker container:
1. Name your dump file `drupal.sql`
2. Place it in the `docker/mysql` directory.
When the MySQL container is initialized, it will import this dump file rather than creating an empty database.


*Start the docker environment with VS Code*
1. Clone this Dev Container repository to your local filesystem.
2. Copy the `env-example` file into a new file named `.env`.
3. Make any needed configuration changes in the `.env` file.
4. Open the Dev Container folder in VS Code, selecting to 'Open in Container' when prompted.

VS Code will build and start the necessary docker containers, and display an empty `site` directory in the file explorer.

*Clone your site project into the container*
1. Start a new terminal in VS Code (`^~`). The terminal will start a shell inside the dev container.
2. Clone your site project into the current working directory. By default, the VS Code container maps your user's `.ssh` directory, so your dev container shell has 



### Managing files on your Host filesystem
Instead of managing your project code within a docker volume and accessing it through VS Code, you can also map your code from your host filesystem into docker. Note that this may create performance issues.
