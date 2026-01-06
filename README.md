# SQLite-database
import sqlite3

try:
    sqlite_Connection = sqlite3.connect('temp.db')
    cursor = sqlite_Connection.cursor()
    print("\nDatabase created and connected to SQLite.")

    sqlite_select_Query = "select sqlite_version();"
    cursor.execute(sqlite_select_Query)

    record = cursor.fetchall()
    print("\nSQLite Database Version is:", record)

    cursor.close()

except sqlite3.Error as error:
    print("\nError while connecting to sqlite", error)

finally:
    if sqlite_Connection:
        sqlite_Connection.close()
        print("\nThe SQLite connection is closed.")

output:
Database created and connected to SQLite.

SQLite Database Version is: [('3.50.4',)]

The SQLite connection is closed.
