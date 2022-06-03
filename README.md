Yii PHP Framework Version 2 / NYX Cron Jobs
===================================================

Yii2 NYX Cron Jobs is a Console Crontroller for Yii2 and is responsible to execute jobs in the Crontab.

The current extension is based on [DenisOgr/yii2-cronjobs](https://github.com/DenisOgr/yii2-cronjobs).

[![Latest Stable Version](https://poser.pugx.org/nyx-solutions/yii2-nyx-cron-jobs/v/stable)](https://packagist.org/packages/nyx-solutions/yii2-nyx-cron-jobs)
[![Total Downloads](https://poser.pugx.org/nyx-solutions/yii2-nyx-cron-jobs/downloads)](https://packagist.org/packages/nyx-solutions/yii2-nyx-cron-jobs)
[![Latest Unstable Version](https://poser.pugx.org/nyx-solutions/yii2-nyx-cron-jobs/v/unstable)](https://packagist.org/packages/nyx-solutions/yii2-nyx-cron-jobs)
[![License](https://poser.pugx.org/nyx-solutions/yii2-nyx-cron-jobs/license)](https://packagist.org/packages/nyx-solutions/yii2-nyx-cron-jobs)
[![Monthly Downloads](https://poser.pugx.org/nyx-solutions/yii2-nyx-cron-jobs/d/monthly)](https://packagist.org/packages/nyx-solutions/yii2-nyx-cron-jobs)
[![Daily Downloads](https://poser.pugx.org/nyx-solutions/yii2-nyx-cron-jobs/d/daily)](https://packagist.org/packages/nyx-solutions/yii2-nyx-cron-jobs)
[![composer.lock](https://poser.pugx.org/nyx-solutions/yii2-nyx-cron-jobs/composerlock)](https://packagist.org/packages/nyx-solutions/yii2-nyx-cron-jobs)

## Installation

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

* Either run

```bash
php composer.phar require --prefer-dist "nyx-solutions/yii2-nyx-cron-jobs" "*"
```

or add

```json
"nyx-solutions/yii2-nyx-cron-jobs": "*"
```

to the `require` section of your application's `composer.json` file.

## Configuration

**Step 1:** Set aliase  @runnerScript in console config. This absolutely path to runner script.

```
Yii::setAlias('@runnerScript', dirname(dirname(dirname(__FILE__))) .'/yii');
```

**Step 2:** Add to console config:

```
'controllerMap' => [
       'cron' => [
           'class' => 'nyx\console\controllers\CronController'
       ],
   ],
```

**Step 3:**  Add task to system scheduler (cron on unix, task scheduler on windows) to run every minute:

```sh
* * * * * /path/to/yii/yii cron
```

## Usage

Add in params array with cron sets:
```
'cronJobs' =>[
    'jobs/first'  => ['cron' => '* * * * *'],
    'jobs/second' => ['cron' => '10 * * * *']
]
```

## License

**yii2-nyx-cron-jobs** is released under the BSD 3-Clause License. See the bundled `LICENSE.md` for details.

![Yii2](https://img.shields.io/badge/Powered_by-Yii_Framework-green.svg?style=flat)
