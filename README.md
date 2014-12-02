# jquery html json forms

A jquery implementation of the [draft](http://www.w3.org/TR/html-json-forms/) for
submitting forms encoded as json.

## Usage:

Include the script in your page and any form with an attribute of
enctype set to 'application/json' will submit data with a json payload.

```html
<form enctype='application/json'>
  <input name='places[0][city]' value='New York City'>
  <input type='number' name='places[0][population]' value='8175133'>
  <input name='places[1][city]' value='Los Angeles'>
  <input type='number' name='places[1][population]' value='3792621'>
  <input name='places[2][city]' value='Chicago'>
  <input type='number' name='places[2][population]' value='2695598'>
</form>
```
produces
```js
{
  "places": [
    {
      "city": "New York City",
      "population": 8175133
    },
    {
      "city": "Los Angeles",
      "population": 3792621
    },
    {
      "city": "Chicago",
      "population": 2695598
    }
  ]
}
```

To disable json post submission, call `$.JSONform.disable()`.

To enable, `$.JSONform.enable()`.

Call `$(formElement).JSONencode()` to get a JSON object representing
formElement.

## TODO

* Add support for input types like date, file
* Add support for other input elements like radios, selects, textareas