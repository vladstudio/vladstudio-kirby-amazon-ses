# Vladstudio Kirby Amazon SES plugin

This is a plugin for [Kirby](http://getkirby.com/) that allows you to send email messages using Amazon SES.
It's a wrapper around Dan Myers' SES class.

## Installation

Put the `vladstudio-kirby-amazon-ses.php` file in your `site/plugins` folder.

## How to use it

Go to your site/config/config.php and add the following rules: 

		c::set('email.use', 'amazon');
		c::set('email.amazon.key', 'Your Amazon SES Key');
		c::set('email.amazon.secret', 'Your Amazon SES Secret');
	
Optional default values:
		
		c::set('email.from', 'John Doe <john@doe.com>');
		c::set('email.replyto', 'John Doe <john@doe.com>');
		c::set('email.subject', 'This is my default subject');
		
## Example usage

    <?php 
    
    $send_result = amazon_ses(array(
      'to'      => 'John Doe <john@doe.com>',
      'from'    => 'Max Musterman <max@musterman.com>',
      'subject' => 'My first Email',
      'body'    => 'Hello my friend! How are things going?'
    ));
    
    ?>

Example of positive response:

	Array
	(
	  [MessageId] => 0000012dc5e4b4c0-b2c566ad-dcd0-4d23-bea5-f40da774033c-000000
	  [RequestId] => 4953a96e-29d4-11e0-8907-21df9ed6ffe3
	)

For more information about response, please visit <http://www.orderingdisorder.com/aws/ses/>.

## Author

Author: Vlad Gerasimov <http://vladstudio.com>  
Based entirely on SES PHP class * Copyright (c) 2011, Dan Myers.  
<http://sourceforge.net/projects/php-aws-ses/>.  
Which is in turn based on Donovan Schonknecht's Amazon S3 PHP class, found here:  
<http://undesigned.org.za/2007/10/22/amazon-s3-php-class>
