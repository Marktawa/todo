# Todo App using PHP and SQLite

To run this PHP code in a GitHub Codespace, you'll need to follow these steps:

1. Set up a GitHub Codespace:
   - Go to your GitHub repository
   - Click on the "Code" button
   - Select the "Codespaces" tab
   - Click "Create codespace on main"

2. Once your Codespace is ready, you'll need to set up the environment:

   a. Install PHP and SQLite:
      ```sh
      sudo apt-get update
      sudo apt-get install php php-sqlite3 sqlite3
      ```

   b. Install Composer (PHP dependency manager):
      ```sh
      curl -sS https://getcomposer.org/installer | php
      sudo mv composer.phar /usr/local/bin/composer
      ```

3. Create the project structure:
   ```sh
   mkdir db
   ```

4. Create a `composer.json` file:
   ```sh
   composer init --no-interaction
   ```

   

   ```sh
   composer init --require ext-pdo:^1.0 --no-interaction
   ```

5. Install dependencies <!--(in this case, just PDO)-->:
   ```sh
   composer require ext-pdo
   ```

   ```sh
   composer install
   ```

   OR

   ```sh
   composer install --ignore-platform-req=ext-pdo
   ```

6. Create the SQLite database:
   ```sh
   sqlite3 db/sqlite.db
   ```
   
   In the SQLite prompt, create the todos table:
   ```sql
   CREATE TABLE todos (
     id INTEGER PRIMARY KEY AUTOINCREMENT,
     description TEXT,
     complete INTEGER DEFAULT 0
   );
   ```
   Exit SQLite with `.quit`

7. Create a file named `index.php` and paste your provided code into it.

8. Start a PHP development server:
   ```
   php -S 0.0.0.0:8080
   ```

9. GitHub Codespaces will detect the running application and provide you with a link to view it. Click on the link to open your Todo List application.

Remember that this setup is for development purposes. For a production environment, you'd want to use a more robust web server like Apache or Nginx.

Also, note that the Codespace environment is ephemeral. If you want to persist your data between sessions, you might want to consider using a more persistent storage solution or committing your SQLite database to your repository (though this isn't generally recommended for larger applications).

