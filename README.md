# About

Easily add notes to any record in WinterCMS through a Mac OS-like user experience.

<p align="center">
    <img src="https://github.com/wintercms/wn-notes-plugin/raw/main/assets/images/screenshot.png?raw=true" alt="Screenshot of Notes FormWidget" width="100%" />
</p>

# Installation

To install it with Composer, run `composer require wintercms/wn-notes-plugin` from your project root.

To install from [the repository](https://github.com/wintercms/wn-notes-plugin), clone it into `plugins/winter/notes` and then run `composer update` from your project root in order to pull in the dependencies.

# Documentation

Simply add the `notes` MorphMany relationship to your model and add a field with a type of `notes` to your fields.yaml to get started.

Example `fields.yaml`:

```yaml
fields:
    name:
        label: Name
        span: full

tabs:
    fields:
        notes: # The name of the relationship the FormWidget will use
            label: ''
            tab: Notes
            type: notes
            span: full
            # autosaveDelay: 2000 # The amount of milliseconds to delay after typing stops to trigger an autosave
            # dateFormat: 'Y-m-d H:i:s' # the php date format for updated_at column
```

Example MorphMany Relationship definition:

```php
public $morphMany = [
    'notes' => [\Winter\Notes\Models\Note::class, 'name' => 'target']
];
```
