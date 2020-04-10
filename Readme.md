# Laravel Nova: Inline Boolean

Adds the ability to edit a boolean field directly from the index or detail page of a resource.

![](https://raw.githubusercontent.com/smart145/inline-boolean/master/InlineBooleanIndex.png)

![](https://raw.githubusercontent.com/smart145/inline-boolean/master/InlineBooleanDetail.png)

## Prerequisites
 - [Laravel](https://laravel.com/)
 - [Laravel Nova](https://nova.laravel.com/)

## Installation

```
$ composer require smart145/inline-boolean
```

## Usage

Use the `MarkRassamni\InlineBoolean\InlineBoolean` field in your Nova resource:

```php
use MarkRassamni\InlineBoolean\InlineBoolean;

class MyResource extends Resource
{
    public function fields(Request $request)
    {
        return [
            InlineBoolean::make('Enabled')
                ->inlineOnIndex()  // Use inline field on the index page
                ->inlineOnDetail()  // Use inline field on the detail page
                ->enableMessage('Boolean has been enabled.')  // Toast message when enabling boolean
                ->disableMessage('Boolean has been disabled.')  // Toast message when disabling boolean
                ->trueText('Enabled')  // Change the text describing true boolean values
                ->falseText('Disabled')  // Change the text describing false boolean values
                ->showTextOnIndex()  // Show true/false text beside the checkbox on the index page
        ];
    }
}
```
