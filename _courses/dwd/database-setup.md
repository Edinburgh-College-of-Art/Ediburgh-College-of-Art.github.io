---
layout: page
title: Database Setup
course: Dynamic Web Design
repo_url: dynamic-web-design
order: 2
---

1. Go to `AboveWebRoot` `>` `autoload` `>` `DatabaseConnection.php`
2. create a file called

```php
class DatabaseConnection {

	static function connect() {
		  return new DB\SQL(
			'mysql:host=localhost;port=3306;dbname=UUN',
			'UUN',
			'PASSWORD'
		  );
	}

}
```

Refer to the `database_info.txt` for your <PASSWORD>.
