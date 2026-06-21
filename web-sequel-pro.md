# Web: Sequel Pro
Here, we are given an unprivileged user’s account credentials (ctf:ctf), but we must get to the admin’s page. Testing for a simple SQL injection using `‘ OR 1 = 1 --` , we are given the following error:

`Fatal error: Uncaught mysqli_sql_exception: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''' at line 1 in /var/www/html/login.php:22 Stack trace: #0 /var/www/html/login.php(22): mysqli->query('SELECT * from u...') #1 {main} thrown in /var/www/html/login.php on line 22`

Here, we can see how important errors are. Not only it confirms our guesses, but also gives us the syntax used (probably `SELECT * from users where user = ‘` … )

The problem was with the comment part, given that MySQL syntax either `#` or a whitespace after `--`. Replacing it, we get the secret:  SSS{yummy_and_nutritious}
