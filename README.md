# Modern Tribe Coding Standards

The Modern Tribe Coding Standard is a set of [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) 
rules for use primarily with the [SquareOne](https://github.com/moderntribe/square-one) framework.

## Requirements

- PHP ^8.0

## Install

Composer v2:

```bash
composer require --dev moderntribe/coding-standards "^3.0"`
```

Composer v1:

Add to the `repositories` object:

```json
    {
      "type": "vcs",
      "url": "git@github.com:moderntribe/coding-standards.git"
    }
```

And `require-dev`:

```json
  "moderntribe/coding-standards": "^3.0"
```

## Project ruleset

> Ensure you're running PHP 8.0 locally!

To use this ruleset, create a `phpcs.xml.dist` in the root of the project and add the following content:

```xml
<?xml version="1.0"?>
<ruleset>
	<arg name="basepath" value="." />
	<arg name="extensions" value="php" />
	<arg name="severity" value="4" />
	<arg name="tab-width" value="4" />
	<arg name="parallel" value="80" />
	<arg name="colors" />

	<!--  Update to the PHP version your production/local docker container runs on -->
	<config name="testVersion" value="8.0" />
	<!-- php -r 'echo PHP_VERSION_ID;' -->
	<config name="php_version" value="80022" />

	<!-- Fix WordPress's terrible typing breaking PHPCS -->
	<config name="minimum_supported_wp_version" value="5.6.0" />

	<!-- Ignore warnings, show progress of the run and show sniff names -->
	<arg value="nps" />

	<!-- Directories to be checked -->
	<file>./wp-content/plugins/core</file>
	<file>./wp-content/themes/core</file>
	<file>./wp-content/mu-plugins</file>

	<!-- Exclude files -->
	<exclude-pattern>*-config.php</exclude-pattern>
	<exclude-pattern>*vendor/</exclude-pattern>
	<exclude-pattern>*tests/*</exclude-pattern>
	<exclude-pattern>*.twig</exclude-pattern>
	<exclude-pattern>*webpack/</exclude-pattern>

	<!-- Include the Modern Tribe coding standard -->
	<rule ref="ModernTribe" />
</ruleset>
```

> Add `phpcs.xml` to your `.gitignore`
 
## Manual Usage

**PHPCS**
```bash
./vendor/bin/phpcs --standard=ModernTribe /path/to/files/**.php
```

**PHPCBF**
```bash
./vendor/bin/phpcbf --standard=ModernTribe /path/to/files/**.php
```

## Resources:

- [SquareOne Framework](https://github.com/moderntribe/square-one)
- [Documentation](https://github.com/moderntribe/square-one/blob/main/docs/tooling/phpcs.md)
