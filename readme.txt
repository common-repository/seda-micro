=== SedaMicro ===
Contributors: wp4hr
Tags: content,upload,citizenjournalism
Requires at least: 4.0.1
Tested up to: 4.4.2
Stable tag: 4.3
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

SedaMicro allows editors to give readers an option to upload media files directly and without registration to their website.

== Description ==
SedaMicro allows editors to give readers an option to upload media files directly and without registration to their website. This is best used for Citizen Journalists that want to document their observations without having to register at the destination website.

We recommend using Amazon S3 being used as the WordPress storage, so that one website can interface with citizen journalists and collect the media files. Other websites can connect to the same S3 instance and use the files uploaded after moderations.

Uploaded images will be stripped of their geotags for anonymity. However, editors are advised to moderate the content such that identity of their users are not revealed.

We maintain manuals in our GitHub page under the /manuals/ directory: https://github.com/icthr/sedamicro

==Installation==
Step 1:

* Install Imagick and NumberFormatter, if not already installed on webserver

 * http://php.net/manual/en/intl.setup.php  → for handling Farsi input from users

 * http://php.net/manual/en/imagick.setup.php → for removing Image geotags from user photos

Step 2: 

* Create an S3 Bucket specifically for the uploaded content

Step 3:

* For Drupal installation: 

 * Install and enable the modules needed for Seda-Mirco and their dependencies:
  * AWS SDK for PHP 
  * Chaos tools 
  * Composer Manager 
  * S3 File System
  * Libraries
  * System
 * Configure S3 plugin
 * Install Seda-Micro, and make sure all dependencies are met
 * Drupal does not have a default “file browser” and gallery, so pick a plugin

* For Wordpress installation:
 * Install the Amazon S3 plugin and configure it.
 * Install Seda-Micro plugin.
 * Add at least one page with `[sedamicro-form]` shorthand to embed the upload form.

Step 4:

* Install SedaMicro Android app on a cellphone with access to the internet.

* Update the settings menu to point to this page created above.
 * Alternatively, to have a larger coverage of users with different setups, we enabled direct access to uploader.
 * Create one or more posts with shorthand code [seda-micro] in them. This will be replaced by the upload form.
  * You will need to distribute the URL of these pages.

Step 5: 

* Users can use the app or a web browser to upload audio files (and image or videos if web server permits)

* The WP/Drupal should also be configured to accept the types. This is to prevent PHP/CGI/Exe files from being uploaded
 * Settings for allowed file types are inherited from WP/Druapl

* Provided Android app allows users to record audio files. They can also select existing media files from their library

* The captcha is to prevent scripted mass bombardment of storage with files

Step 6:

* To display or use uploaded files:

 * In Wordpress you can directly browse in the gallery, or use template pages that list gallery items
 * In Drupal, content management is left to the administrator. There are multiple plugins available that allow such gallery viewing or image insertion.

== Screenshots ==
1. The page that will show the upload form. Note the included shorthand tag.
2. Generated page with added upload form.
3. View in the Android app. Users can use their browser directly as well.
