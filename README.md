# Language Toggle

This solution utlizes jQuery and assumes that the page is statically loaded, with
no dynamic components added in after page load.

## Using

All code is expected to be on the page.

The root html element needs to be marked by the "glossary" class.

You must specify the language of the page on the glossary element with the data-lang attribute:

```
<main class="glossary" data-lang="english">
```

This will be used to determine the proper language to show. All text variants are present
in the html and are toggled on or off based on whatever value is set in that data-lang

## Defining definitions

Every element that is intended to be toggled should have two classes: `lang`, and the selected language.
For example an english language span would look like:

```
<span class="lang english">English Description</span>
```

Elements with the `lang` class should _not_ be nested within each other. Doing so will have
unpredictable behavior

As delivered there are two languages supported: English (the default), and Spanish.

## Linking to definitions

Ever term definition component should include an anchor element with a unique name, for example:

```
<a name="able_to_work"></a>
```

This will allow linking directly to the component via url, just append `#able_to_work` to the
end of the glossary page's url.

## Defining terms

Terms should have the structure of:

```
 <li class="term" data-category="aad">
    <a name="UNIQUE_KEY_FOR_LINKING"></a>
    <ul class="term-name">
        <li class="lang spanish">SPANISH_TERM</li>
        <li class="lang english">ENGLISH_TERM</li>
    </ul>

    <div class="definitions">
        <div class="definition lang english">
        ENGLISH_DEFINITION
        </div>
        <div class="definition lang spanish">
        SPANISH_DEFINITION
        </div>
    </div>
 </li>
```

Important note: while the definitions can be in any order, the English term should be the last element
in the ul.term-name tag. This is because the English term name will always be visible.
