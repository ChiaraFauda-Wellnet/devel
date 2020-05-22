[[_TOC_]]

#### Introduction

Devel module contains helper functions and pages for Drupal developers and
inquisitive admins:

 - A block for quickly accessing devel pages
 - A block for masquerading as other users (useful for testing)
 - A mail-system class which redirects outbound email to files
 - Drush commands such as fn-hook, fn-event, ...
 - *Webprofiler*. Adds a debug bar at bottom of all pages with tons of useful
 information like a query list, cache hit/miss data, memory profiling, page
 speed, php info, session info, etc.
 - *Devel Generate*. Bulk creates nodes, users, comment, terms for development. Has
 Drush integration.

This module is safe to use on a production site. Just be sure to only grant
_access development information_ permission to developers.

#### DrupalSpoons
https://gitlab.com/drupalspoons/devel is our workplace for code, MRs, and CI. See
[DrupalSpoons](https://gitlab.com/drupalcontrib/webmasters/-/blob/master/README.md)
for more info. We push back to git.drupalcode.org in order to keep
[Security Team](https://www.drupal.org/security) coverage and packages.drupal.org integration.

#### Local Development
1. Clone devel `git clone https://git.drupalcode.org/project/devel.git`
1. `cd devel`
1. Assemble a codebase (i.e. get Drupal core). `composer install`. Your source tree now looks like: ![Folder tree](/icons/folders.png)
1. Install a testing site `composer si`
1. Configure a web server to serve devel's `/web` directory as docroot. __Any__ of these works fine:
    1. `composer runserver`
	1. Setup Apache/Nginx/Other. A virtual host will work fine. Any domain name works.
	1. docker-compose.yml is available for local development if you wish. More info at [wodby/php](https://github.com/wodby/php).

#### Testing
- [CI docs](https://gitlab.com/drupalspoons/webmasters/-/blob/master/docs/ci.md) give info on running tests.
- See [develCommandsTest.php](tests/src/Functional/DevelCommandsTest.php) for an example of Drush command testing. This uses Drush's own test framework, based on PHPUnit.

#### Maintainers

See https://gitlab.com/groups/drupaladmins/devel/-/group_members.