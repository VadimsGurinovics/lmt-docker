# Simple Docker setup for LMT Backend Task

### Step 1: Clone the repository

Clone the repository:

git clone https://github.com/VadimsGurinovics/lmt-docker.git

### Step 2: Navigate to the project directory

First, make sure you're inside the project folder:

```bash
cd lmt-docker/
```
### Step 3: Clone Laravel project inside previously cloned Docker structure www directory

Clone one of the Laravel projects inside the `www` directory. Here are the links to the repositories:
https://github.com/VadimsGurinovics/lmt-backend-task-no-ddd

https://github.com/VadimsGurinovics/lmt-backend-task-ddd

Basically 'www' directory is just example where you Laravel project will be located. Most likely commands will be:
```bash
rm -rf www/
git clone https://github.com/VadimsGurinovics/lmt-backend-task-no-ddd.git www
```

### Step 4: Build and run the Docker container

Use the following command to build and run the application in Docker:

```bash
docker compose up -d --build
```

### Step 5: Access the running Docker container

Run this command to enter the container:

```bash
docker exec -it web-app-lmt bash
```

### Step 6: Verify you're in the correct directory

Check that you're in the `/app` directory by executing:

```bash
pwd
```

You should see:

```
/app
```

### Step 7: Install Composer dependencies and execute other commands

Inside the container, run the following commands to install all PHP dependencies, migrate the database, execute tests
etc.

```bash
cp .env.example .env
composer install
php artisan key:generate
php artisan migrate
php artisan migrate --env=testing
php artisan test
```
