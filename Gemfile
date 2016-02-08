source 'https://rubygems.org'

puppet_version = ENV.key?('PUPPET_VERSION') ? "= #{ENV['PUPPET_VERSION']}" : ['>= 2.7']
parallel_version = RUBY_VERSION.start_with?("1.8") ? "= 1.3.3" : nil

# FIXME: get rid of this pattern magic ..
if RUBY_VERSION =~ /^2\.(2|3)\./ && puppet_version =~ /^= 3.(7|8)\./
  gem "safe_yaml"
end

gem "rake"
gem "puppet", puppet_version
gem "builder"
gem "parallel", parallel_version

gem "hiera"
gem "hiera-puppet"


group :test do
  gem "mocha", "~> 0.13", :require => false

  if RUBY_VERSION =~ /^2\.(2|3)/
    gem "test-unit"
  end
end
