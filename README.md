![Logo sqStorage](https://www.picflash.org/img/2018/12/31/hwxkb96wq17sfvu.png "Logo sqStorage")

A easy to use and super quick way to organize your inventory, storage and storage areas.

### Note
Right now sqStorage is available in German and English. Feel free to add your own translation (see LANGUAGE.md for details on how to do so).

### Installation and usage

#### Requirements

* PHP version 7.0 and upwards
  * PHP extensions: `mysqli`, `gettext`, `intl`
* a MySQL-compatible database server (e.g. MariaDB)
* a web server, e.g. nginx or Apache.

#### Database

Default database: `tlv`
Default username: `tlvUser`
Default password: `tlvUser`

This can be configured in `support/dba.php` by changing the `DB::dbName`, `DB::$user` and `DB::$password` variables. If your database is on a different server, you might want to use the IP or hostname instead of `localhost`.

#### Permissions

The directories `smartyfiles/` and `languages/locale/` need to be **writeable** for the webserver.

`chown -R www-data smartyfiles/` and `chown -R www-data languages/locale/` should work in most cases.

#### First run

- Once user and database are created, open `bootDB.php`. This will create all DB tables necessary.
- Open sqstorage in your webbrowser and create a admin account.
  * this can be done only once after installation!
  * If you mess up, you will have to drop/truncate the `users` table in order to prompt for admin account registration again. You will have to open `bootDB.php` again to recreate the tables.
  
#### Custom fields

If you are upgrading of an earlier version of sqStorage, the custom fields code might have changed. This fields had been implemented earlier but where of no practical use. Still possible so, you might have to **update your database** in order to make use of the latest features.

##### Updating the database for usage of custom fields
In any case it is a good idea to open the database and **dropping** the `customFields` and `fieldData` tables. After dropping the tables, visit or execute `bootdb.php` to let the tables be created. After that, you can already use custom fields - even so this feature is not yet completely finished, but the data structure will not change anymore in the future.

#### German talking src ressource
The whole idea behind sqStorage or "Tom's Invetarverwaltung" can be found at the german bulletin board NGB.to over https://ngb.to/threads/39122-Webbasierte-Mini-Lagerverwaltung

#### Chatroom
There is a **Matrix chat room** at Tilde.fun where development and or general talk about features and such can be brought in:
https://chat.tilde.fun/#/room/#sqstorage:tilde.fun

#### Last but not least

Have fun using sqStorage and do not hesitate to write a email or issue, if you miss something!
