Warden
=======

Warden is a centralized dashboard to administer Drupal sites updates.

I tried to implement it using containers, but I'm getting errors running the required cron commands to register the sites.

# Setting up

- Clone https://github.com/teamdeeson/warden into app folder
- Run composer install --ignore-platform-reqs
- When asked for keys, set /var/www/encryption/key.public and /var/www/encryption/key.private
- When asked for email: mailhog:1025 no user, no password

# Problems found

When running `php bin/console deeson:warden:warden-cron --import-new` from php container it returns error:

```
In DocParser.php line 995:

  Notice: Trying to access array offset on value of type null


deeson:warden:warden-cron [--import-new] [-h|--help] [-q|--quiet] [-v|vv|vvv|--verbose] [-V|--version] [--ansi] [--no-ansi] [-n|--no-interaction] [-e|--env ENV] [--no-debug] [--] <command>In DocParser.php line 995:

  Notice: Trying to access array offset on value of type null


deeson:warden:warden-cron [--import-new] [-h|--help] [-q|--quiet] [-v|vv|vvv|--verbose] [-V|--version] [--ansi] [--no-ansi] [-n|--no-interaction] [-e|--env ENV] [--no-debug] [--] <command>
```

I got stuck at this point. I need to look back at this later if this is still interesting.