yii2-validators
===================

Yii2-validators are validators for yii for some specific cases that are not covered by standard yii2 validators. Currently it holds only WordCount validator but it will be extended in future.

## Installation

The preferred way to install this extension is through [composer](http://getcomposer.org/download/). Check the [composer.json](https://github.com/bitdevelopment/yii2-validators/blob/master/composer.json) for this extension's requirements and dependencies.

To install, either run

```
$ php composer.phar require bitdevelopment/yii2-validators "dev-master"
```

or add

```
"bitdevelopment/yii2-validators": "dev-master"
```

to the ```require``` section of your `composer.json` file.

## Latest Release

> NOTE: The latest version of the module is v1.0.0.

## Usage

Add validator to your rules list in your model

```php
use bitdevelopment\yii2-validators\WordValidator;

class Post extends \yii\base\Model {

  public function rules() {
    return [
            [['myField'],WordValidator::className(),'min'=>200,'max'=>500]
    ];
  }
  ...
```
If you want to validation occurs while user is typing you can use validateOnType option, for example:
```php
$form->field($model, 'comment',['validateOnType' => true])->textarea([
                    'rows'=> 15
            ]);
```
