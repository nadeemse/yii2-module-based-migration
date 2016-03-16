
Module based migration.
=======================
Runs module migrations from module 'migrations' folder.
Use it if you want to keep your module migrations inside module 'migrations' folder.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist nadeemse/yii2-module-based-migration "*"
```

or add

```
"nadeemse/yii2-module-based-migration": "*"
```

to the require section of your `composer.json` file.


Usage
-----
```
    Redefine migrate controller in your console config file:
    ...
    'controllerMap' => [
        'migrate'   => 'nadeemse\moduleMigration\ModuleMigrateController'
    ],
    ...

    Also define 'modules' app attribute here like in web app config file, e.g.:
    ...
    'modules'   => [
        'user'  => 'app\modules\user\Module',
        'page'  => [
            'class' => 'app\modules\base\modules\Module'
        ]
    ],
    migrations from your moduleFolder/migrations will be applied.
```

Since 1.3.0 there is also migrate/data-dump {tableName} action
    - for generating any table data migration into @app/migrations folder.

Since 1.2.0 you may use new commands:
```
./yii migrate/module-up yourModuleName
./yii migrate/module-down yourModuleName
```