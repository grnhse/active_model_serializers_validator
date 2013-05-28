# ActiveModel::Serializer::Validator

This gem adds JSON schema validations for output generated by an `ActiveModel::Serializer`.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'active_model_serializers_validator'
```

## Usage

The gem adds one instance method and one class method to the `ActiveModel::Serializer` class, `#valid?` and `.json_schema`:

```ruby
class MySerializer < ActiveModel::Serializer
  json_schema '/path/to/my/schema.jsonschema'

  attribute :foo
end

serializer = MySerializer.new(OpenStruct.new(foo: 'bla'))

serializer.valid?
# => false

serializer.errors
# => [The property '#/foo' of type String did not match the following type: integer in schema /path/to/my/schema.jsonschema]
```

## Todo

* Add more features! :smile:

## License

`ActiveModel::Serializer::Validator` is © 2013 [Mirego](http://www.mirego.com) and may be freely distributed under the [New BSD license](http://opensource.org/licenses/BSD-3-Clause).  See the [`LICENSE.md`](https://github.com/mirego/active_model_serializers_validator/blob/master/LICENSE.md) file.

## About Mirego

Mirego is a team of passionate people who believe that work is a place where you can innovate and have fun.
We proudly built mobile applications for
[iPhone](http://mirego.com/en/iphone-app-development/ "iPhone application development"),
[iPad](http://mirego.com/en/ipad-app-development/ "iPad application development"),
[Android](http://mirego.com/en/android-app-development/ "Android application development"),
[Blackberry](http://mirego.com/en/blackberry-app-development/ "Blackberry application development"),
[Windows Phone](http://mirego.com/en/windows-phone-app-development/ "Windows Phone application development") and
[Windows 8](http://mirego.com/en/windows-8-app-development/ "Windows 8 application development").
