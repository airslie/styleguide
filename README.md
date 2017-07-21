# airslie-style

Airslie shared style configs.

## Installation

Add this line to your application's Gemfile:

```ruby
group :test, :development do
  gem 'airslie-style'
end
```

Or, for a Ruby library, add this to your gemspec:

```ruby
spec.add_development_dependency 'airslie-style'
```

And then run:

```bash
$ bundle install
```

## Usage

Create a `.rubocop.yml` with the following directives:

```yaml
inherit_gem:
  airslie-style:
    - default.yml
```

Now, run:

```bash
$ bundle exec rubocop
```

You do not need to include rubocop directly in your application's dependences. Airslie-style will include a specific version of `rubocop` and `rubocop-rspec` that is shared across all projects.

To re-release a new version of this gem

```
# Change version in lib/style/version
# Commit the changes locally
$ OVERCOMMIT_DISABLE=1 bundle exec rake release
```
