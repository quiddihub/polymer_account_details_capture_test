# Dojono Developer test

## Bank Account Capture and Validation
This test requires the participant to create a v2 Polymer component, complete with any associated configuration information to support a `bower install`. The component must;

1. capture bank account (8 digits) and sort code (6 digits) in accordance with the norms of capturing such data elements.
2. validate the account number and sort code against our API and;
  * indicate to the user that the data is invalid,
  * allow the component container to be aware of the data and the state of the validation.
3. use the minimum number of components possible. You must;
  * restrict yourself to [paper elements](https://www.webcomponents.org/collection/PolymerElements/paper-elements) (and their dependancies) for data capture and user interaction,
  * use one other library (and its dependancies) of your choice for interacting with the API,
  * use [iron-icons](https://www.webcomponents.org/element/PolymerElements/iron-icons) if you wish.

## API
The test Bank Check API accepts a request with the Account number and Sort Code. As Account numbers and Sort Codes are linked they cannot be validated independently. The service can be found at https://api.dojono.co.uk/api/bank_check. The route accepts a JSON payload containing the Account number and Sort Code as follows;
```javascript
{
  "account": "12001039",
  "sort_code": "083210"
}
```

The API will respond with a JSON payload reflecting the status of the information.
### Valid
```javascript
{
  "valid": true
}
```

### Invlid
```javascript
{
  "valid": false
}
```
