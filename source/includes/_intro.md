# Avvo API

## Getting Access

To use the API, you must have an Avvo account with some extra privileges. Contact [Dave French](mailto:dfrench@avvo.com) to get set up.

## Using the API

The API uses [HTTP Basic authentication over SSL](http://en.wikipedia.org/wiki/Basic_access_authentication). You must supply your Avvo username and password with each request. The linked Wikipedia page shows some examples on how to do this, but most programming languages and system tools should include built-in support for this.

Detailed documentation for each possible action, including the URL endpoint and required parameters, are accessible from the sidebar to the left. All Avvo API responses will be returned in JSON, which is human-readable. JSON parsers are also available for nearly every language. Example responses are shown on the API detail pages.

## Format

We format our responses in JSON according to the [Json API](http://jsonapi.org/) standard.