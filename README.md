# Postmarkapp Mailer for SilverStripe

## Maintainer Contact 
 * Will Rossiter 
   <will (at) fullscreen (dot) io>
	
## Requirements
 * SilverStripe 2.3 or newer.
 * PHP5.3 or higher for supporting inbound hooks.

## Overview

This module provides a Postmark (http://postmarkapp.com/) mailer subclass for 
use within SilverStripe projects. It is actually a tiny wrapper around the 
existing PHP libraries for Postmark:

	- https://github.com/Znarkus/postmark-php.git
	- https://github.com/jjaffeux/postmark-inbound-php.git

The module hooks transparently into your SilverStripe installation via 
__Email::set_mailer();__.

You can use set_mailer on a per instance or environment basis so that production
emails are set through Postmark while in development SMTP is used.

## How to use

 * Sign up to Postmarkapp (http://postmarkapp.com)
 * Create your first server and signature through the postmarkapp dashboard.
 * Define your POSTMARKAPP_API_KEY and POSTMARKAPP_MAIL_FROM_ADDRESS variables
 in your SilverStripe project. 

Place the following in your _config.php

	define('POSTMARKAPP_MAIL_FROM_NAME', 'Your Name');
	define('POSTMARKAPP_MAIL_FROM_ADDRESS', 'mailer@yourdomain.com');
	define('POSTMARKAPP_API_KEY', '...5aef660..');
	
 * Set the Mailer to be your SilverStripe Mailer instance, Again, place this in 
 your _config.php or before the code you need to send the email:

	Email::set_mailer('PostmarkMailer');

	
## Known Issues

Currently I have only been using this for simple text emails from a SaaS 
application and haven't tested some of the other functionality. For 
example attaching files, customizing emails (reply to, cc)

If you need a missing feature please fork, contribute or get in touch.

## License

This module is released under the BSD license. Both the Postmark PHP library
and the Postmark Inbound PHP library are released under the MIT License.

http://www.opensource.org/licenses/mit-license.php
