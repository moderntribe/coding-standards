# Modern Tribe Coding Standards

The Modern Tribe Coding Standard is a set of [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) 
rules for use primarily with the [SquareOne](https://github.com/moderntribe/square-one) framework.

## Install

Composer v2:

`composer require --dev moderntribe/coding-standards`

Composer v1:

Add to the `repositories` object:

```json
    {
      "type": "vcs",
      "url": "git@github.com:moderntribe/coding-standards.git"
    },
```

And `require-dev`:

```json
  "moderntribe/coding-standards": "^1.0",
```

## Resources:

- [SquareOne Framework](https://github.com/moderntribe/square-one)
- [Documentation](https://github.com/moderntribe/square-one/blob/main/docs/tooling/phpcs.md)
