# How to use the PySpectrometer DB module
   ## Requirements:
   1. Update, install and upgrade pip
      ```shell
      sudo apt update
      sudo apt install python3-pip
      pip3 --version
      sudo pip3 install --upgrade pip
      ```
   2. Set up the .env file
      ```shell
      sudo cp src/.env.example src/.env
      ```

   ## Installation:
   1. Create a new virtual environment
       ```shell
       python3 -m venv .venv
       ```
   2. Activating the .venv
      ```shell
      source .venv/bin/activate
      ```
   3. Install requirements on the .venv
      ```shell
      pip3 install -r requirements.txt
      ```

   ## Initialize database:
   ### Local / Development Environment:
   1. Run the `db.py` module with the initialize argument:
      ```shell
      python3 src/db.py --initialize
      ```
      > This creates a new local SQLite3 database in the root folder of this project.
      ![db_file.png](media/db_file.png)
   2. Run the `db.py` module again with the test argument:
      ```shell
      python3 src/db.py --test
      ```
      > This will create two test entries into the new created database at `measurements` table.  
      You can delete them after verifying that it works.  
      ![db_test_entries.png](media/db_test_entries.png)
   ### Production Environment:
   > Following soon...

Now, if you run any of the PySpectrometer2 scripts, it should, based on the DB_TYPE (`sqlite3`, `postgresql`) from the .env 
file, pick the correct database and write the data to the database whenever a new .csv file is generated.

