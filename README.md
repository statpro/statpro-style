# statpro-style

Statpro shared style configs.

##Inheriting configuration from a remote URL
https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_markup_formatting_ref/BulletedLists.html
The optional inherit_from directive can contain a full url to a remote file. This makes it possible to have common project settings stored on a http server and shared between many projects.

The remote config file is cached locally and is only updated if:

- The file does not exist.
- The file has not been updated in the last 24 hours.
- The remote copy has a newer modification time than the local copy.

You can inherit from both remote and local files in the same config and the same inheritance rules apply to remote URLs and inheriting from local files where the first file in the list has the lowest precedence and the last one has the highest. The format for multiple inheritance using URLs is:

```yaml
inherit_from:
- http://www.example.com/rubocop.yml
- http://raw.githubusercontent.com/statpro/statpro-style/master/default_rubocop.yml
- ../.rubocop.yml
  You can inherit from a repo with basic auth that is authorized to access the repo as follow:
```

```yaml
inherit_from:
- http://<user_name>:<password>@raw.github.com/example/rubocop.yml
  A GitHub personal access token can also be configured as follow:
```

```yaml
inherit_from:
- http://<personal_access_token>@raw.github.com/example/rubocop.yml
```
