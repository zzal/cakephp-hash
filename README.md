cakephp-hash
============

**Please note that this package is in alpha develpment phase.**


This package (intended for Laravel 4) gives you the ability to use the great cakePHP’s Hash class into your Laravel 4 projects.

[See cakePHP documentation.](http://book.cakephp.org/2.0/en/core-utility-libraries/hash.html)

## Installation

Install this package through Composer. To do so, edit your project's `composer.json` file to require `zzal/cakephp-hash`.

    "require": {
		"zzal/cakephp-hash": "dev-master"
	}
	
Then, add this inside the "autoload" section of this file:

	"autoload": {
		"classmap": [
			…
		],
        "psr-0": {
        	"CakePHP\\Utility\\": "vendor/cake/Hash"
        }


Finally, update Composer from the Terminal:

    composer update

