# Deprecating an API

## Why

> provide background information, problem description, challanges and/or goals.

* increase support of latest APIs
* decrease outdated software

## What

> The topic details, describe the tool / technology in detail, prefer linking to external sources if a 3rd party

- use a header
- update swagger
- updaet readme

## How

> The **TELUS context** of how we're using the described topic, provide **deep details** here, including usage manual, API documentation, operational guidelines, etc...

### Add a header

Add the following header:

```
Warning: 299 - "Deprecated API : use /vX instead."
```

This can be done with ExpressJS with the following snippet:

```js
router.use((req, res, next) => {
  res.setHeader('Warning', '299 - "Deprecated API: use /vX instead."')
  return next()
})
```

### Update Swagger documentation

There are two places to update:

* api-platform-docs2
* your main swagger file

### Update README

A table?

|Version|Is Deprecated?|Is Shutdown?|
|---|---|---|
|`/v1`|Yes|Yes (2015-01-23)|
|`/v2`|Yes|No|
|`/v3`|No|No|

## Who

- Magnum API
- API Platform

## References

- [Convention for HTTP response header to notify clients of deprecated API](https://stackoverflow.com/a/29623798/298281)
- [Warning header RFC 7234](https://tools.ietf.org/html/rfc7234#section-5.5)
