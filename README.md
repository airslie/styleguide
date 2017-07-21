# Airslie Style Guide

Airslie shared style configuration and guide.

## Rubocop

To use the shared rubocop configuration in a project use the following three files:

.codeclimate.yml
```yaml
prepare:
  fetch:
  - url: "https://raw.githubusercontent.com/airslie/airslie-styleguide/master/rubocop.yml"
    path: "default.yml"
```

.rubocop.yml
```yaml
# Note that the local default.yml is overwritten on CodeClimate with the contents of
# the remote rubocop.yml pulled from GitHub in a codeclimate prepare step.
inherit_from:
  - default.yml
```

default.yml
```yaml
inherit_from:
  - https://raw.githubusercontent.com/airslie/airslie-styleguide/master/rubocop.yml

# Don't add anything to this file other than the inherit_from above
# as this file is overwritten on codeclimate with the contents of the above
# remote url which is downloaded in a codeclimate prepare step.
```

When running locally, rubocop inherits from the remote github styleguide default.yml.
When running on CodeClimate, a prepare step replaces the local default.yml with the remote
styleguide one.
