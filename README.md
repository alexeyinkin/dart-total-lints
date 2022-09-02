[![Pub Package](https://img.shields.io/pub/v/total_lints.svg)](https://pub.dev/packages/total_lints)
[![GitHub](https://img.shields.io/github/license/alexeyinkin/dart-total-lints)](https://github.com/alexeyinkin/dart-total-lints/blob/main/LICENSE)
[![CodeFactor](https://img.shields.io/codefactor/grade/github/alexeyinkin/dart-total-lints?style=flat-square)](https://www.codefactor.io/repository/github/alexeyinkin/dart-total-lints)
[![Support Chat](https://img.shields.io/badge/support%20chat-telegram-brightgreen)](https://ainkin.com/chat)

A very strict set of lints for Dart and Flutter apps.

## Concept

Dart and Flutter come with an analysis tool that points some possible errors and bad styling
that can lead to problems. More on this:
https://dart.dev/guides/language/analysis-options

However, a lot of beneficial rules are disabled by default. This leads to either coding errors
or long linter config that enables individual rules that you copy between projects.

This package is my opinionated choice of rules. Unlike [lints](https://pub.dev/packages/lints)
and [flutter_lints](https://pub.dev/packages/flutter_lints) packages that enable specific rules,
this package aims to enable *all but* specific rules. So every rule is enabled unless it was
considered and deliberately rejected.

You may use this set as a baseline and enable or disable specific rules.

## Usage

1. Add this package under `dev_dependencies` in your `pubspec.yaml`.

2. In your `analysis_options.yaml`, replace the default inclusion with a file from this package.

For applications:
```yaml
include: package:total_lints/app.yaml
```

For packages:
```yaml
include: package:total_lints/package.yaml
```

3. See https://dart.dev/guides/language/analysis-options to disable or enable specific rules.

4. Run analysis with `flutter analyze`.

## Choosing a Set of Rules

### `app.yaml`

This set is used for runnable applications. Their code is not reused, so tedious tasks
on it are not required.

The rules in this set are listed [here](https://github.com/alexeyinkin/dart-total-lints/blob/main/lib/app_2.18.yaml).

### `package.yaml`

This set is used for packages that are used in other apps. A package's code is reusable
by other developers, and the context of its usage is unknown in advance,
so this code should meet a higher standard of maintainability.

This set includes all rules from `app.yaml` plus the rules listed
[here](https://github.com/alexeyinkin/dart-total-lints/blob/main/lib/package_2.18.yaml).

## Using with Older Versions of Dart

For older versions, import a file with specific version, e.g.:

```yaml
include: package:total_lints/package_2.17.yaml
```

The oldest version this package supports is 2.17.
