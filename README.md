Yii PHP Framework Version 2 / NOX Cron Jobs
===================================================

Yii2 NOX Cron Jobs is a Console Crontroller for Yii2 and is responsible to execute jobs in the Crontab.

The current extension is based on [DenisOgr/yii2-cronjobs](https://github.com/DenisOgr/yii2-cronjobs).

Installation
----------

- **Step 1:** The preferred way to install this extension is through [Composer](http://getcomposer.org/download/).

Either run:

```
php composer.phar require --prefer-dist nox-it/yii2-nox-cron-jobs "*"
```

or add:

```
"nox-it/yii2-nox-cron-jobs": "*"
```

to the require section of your `composer.json` file.

- **Step 2:** Set aliase  @runnerScript in console config. This absolutely path to runner script.
```
Yii::setAlias('@runnerScript', dirname(dirname(dirname(__FILE__))) .'/yii');
```
- **Step 3:** Add to console config:
```
'controllerMap' => [
       'cron' => [
           'class' => 'nox\console\controllers\CronController'
       ],
   ],
```
- **Step 4:**  Add task to system scheduler (cron on unix, task scheduler on windows) to run every minute:

```sh
* * * * * /path/to/yii/yii cron
```

Usage
-----

Add in params array with cron sets:
```
'cronJobs' =>[
    'jobs/first'  => ['cron' => '* * * * *'],
    'jobs/second' => ['cron' => '10 * * * *']
]
```

![Yii2](https://img.shields.io/badge/Powered_by-Yii_Framework-green.svg?style=flat)
