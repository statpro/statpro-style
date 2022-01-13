# statpro-style

Statpro shared style configs.

## Installation

Add this line to your application's Gemfile:

```ruby
group :test, :development do
  gem 'statpro-style', :git => 'https://github.com/statpro/statpro-style', :branch => 'master'
end
```

Or, for a Ruby library, add this to your gemspec:

```ruby
spec.add_development_dependency 'statpro-style'
```

And then run:

```bash
$ bundle install
```

## Usage
To allow local developmet linting with rubocop, create a `.rubocop.yml` or `.codeclimate-rubocop.yml` with the following directives:

```yaml
inherit_gem:
  statpro-style:
    - default_rubocop.yml
```
for HAML create a `.codeclimate-haml-lint.yml` file as below. 
```yaml
inherit_gem:
  statpro-style:
    - default_haml-lint.yml
```

For codeclimate to run please add the following to `.codeclimate.yml` to override the commited files. 
- https://docs.codeclimate.com/docs/configuring-the-prepare-step

```yaml
prepare:
  fetch:
    - url: "https://raw.githubusercontent.com/statpro/statpro-style/master/default_rubocop.yml"
      path: ".codeclimate-rubocop.yml"
    - url: "https://raw.githubusercontent.com/statpro/statpro-style/master/default_haml-lint.yml"
      path: ".codeclimate-haml-lint.yml"
```

You do not need to include rubocop directly in your application's dependencies. Statpro-style will include a specific version of `rubocop` and `rubocop-rspec` that is shared across all projects.
