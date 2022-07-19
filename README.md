A very strict set of lints for Dart and Flutter apps.

## Concept ##

Dart and Flutter come with an analysis tool that points some possible errors and bad styling
that can lead to problems. More on this:
https://dart.dev/guides/language/analysis-options

However, a lot of beneficial rules are disabled by default. This leads to either coding errors
or long linter config that enables individual rules that you copy between projects.

This package is my opinionated choice of rules. Unlike [lints](https://pub.dev/packages/lints)
and [flutter_lints](https://pub.dev/packages/flutter_lints) packages that enable specific rules,
this package aims to enable *all but* specific rules. So every rule is enabled unless it was
considered and deliberately rejected.

You may use this set a baseline and enable or disable specific rules.

## Usage ##

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
