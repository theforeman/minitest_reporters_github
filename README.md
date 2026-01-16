# GitHub Reporter for minitest-reporters

[minitest-reporters](https://github.com/minitest-reporters/minitest-reporters) a framework to add additional reporters, but a GitHub version is missing.
https://github.com/minitest-reporters/minitest-reporters/issues/330 has been open for a long time and https://github.com/minitest-reporters/minitest-reporters/pull/332 was opened shortly after, but it was never merged.
This repository has taken the code from that PR and turned it into a standalone gem to be used.
The ideal is still for this reporter to be included in minitest-reporters.

## Usage

In your `test_helper.rb` file, add the following lines:

```ruby
require 'minitest/reporters'

if ENV['GITHUB_ACTIONS'] == 'true'
  require 'minitest_reporters_github'
  Minitest::Reporters.use!([MinitestReportersGithub.new])
else
  Minitest::Reporters.use!
end
```
