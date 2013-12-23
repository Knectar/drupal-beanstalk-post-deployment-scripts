drupal-beanstalk-deplymentscripts
=================================

to be used with Beanstak in the script section, to trigger various Drush functions via commits messages or beanstalkj deploy comments.
Also it keeps a log of Beanstalk deplyments on the server. Developed for @Knectar

Installation
============

add the bellow to the deployments scripts section to run
~~~bash
curl https://raw.github.com/sanguis/drupal-beanstalk-post-deployment-scripts/master/development.sh > /tmp/%USER_NAME%-%REVISION%.sh
bash /tmp/%USER_NAME%-%REVISION%.sh "%COMMENT%" %REVISION% %USER_NAME%
~~~


Usage
=====
To use the keyword bellow to trigger the drush actions.

**-updb-**

drush -y updb


**-fra-**

drush -y fra


**-bigups-**

drush -y updb

drush -y fra

drush cc all


**-cc_all-**

drush cc all

**-cc_cssjs-**

drush cc css-js

**-cc_block-**

drush cc block

TODO
====

* change clear cache function to be *-cc_CACHETYPE-* and have it default to *cc all* but be able to use all of the cache clear types and just read the entry for the *%comment%* var.
* allow custom deploy log vars and locaton.
