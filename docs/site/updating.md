# Updating the site

The CKTOJ is under active development, so occasionally you may wish to update. This is a fairly simple process.


First, switch to the site virtual environment, and pull the latest changes.

```
(cktsite) $ git pull origin master
```

Dependencies may have changed since the last time you updated, so install any missing ones now.

```
(cktsite) $ pip3 install -r requirements.txt
```

The database schema might also have changed, so update it.

```
(cktsite) $ ./manage.py migrate
(cktsite) $ ./manage.py check
```

Finally, update any static files that may have changed.

```
(cktsite) $ ./make_style.sh
(cktsite) $ ./manage.py collectstatic
(cktsite) $ ./manage.py compilemessages
(cktsite) $ ./manage.py compilejsi18n
```

That's it! You may wish to condense the above steps into a script you can run at a later time.
