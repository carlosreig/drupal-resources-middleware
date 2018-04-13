Drupal resources middleware
===============

This is a very simple module for Drupal 7 that just redirects requests.

Motivation
===========

When I migrate an existing Drupal 7 website to my dev environment I don't want to copy all the filesystem since there usually are a lot of files. That implies that the images and other resources are not displayed on my dev installation.

This module just redirects the requests that go to my dev installation of Drupal 7 to the production domain. That allow the images and other resources to be displayed on my local installation and having a dev environment as similar as possible to the production one.

How does it work
============

Very simple. When this module is enabled, all the requests are analyzed to determine if they have to be redirected. A request is redirected in case that it goes to any file located in the public directory (normally `sites/default/files`) and this file does not exist in the local filesystem.


There is a file called `settings.php` with an array with one element called `site_url`. The default value for that item is `http://example.com`- You just have to change `http://example.com` by your production domain and enable the module.
