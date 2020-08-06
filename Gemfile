source "https://rubygems.org"

ruby RUBY_VERSION

DECIDIM_VERSION = { git: 'https://github.com/decidim/decidim.git', branch: '0.19-stable' }

gem 'puma', '~> 3.0'
gem 'uglifier', '>= 1.3.0'
gem 'delayed_job_active_record'
gem "daemons"
gem "whenever"

gem 'figaro', '>= 1.1.1'
gem 'geocoder', '~> 1.6.1'

gem 'decidim', DECIDIM_VERSION
gem 'decidim-cas_client', git: "git@github.com:CodiTramuntana/decidim-cas-client.git"
gem "codit-devise-cas-authenticable", git: "git@github.com:CodiTramuntana/codit-devise-cas-authenticable.git"

# Force gem version to fix:
# undefined method `polymorphic?' for ActiveRecord::Reflection::PolymorphicReflection
# See: https://github.com/activerecord-hackery/ransack/issues/1039
gem 'ransack', '2.1.1'

group :development, :test do
  gem 'byebug', platform: :mri
  gem "better_errors"
  gem "binding_of_caller"
  gem 'faker', "~> 1.8.4"
end

group :development do
  gem 'decidim-dev', DECIDIM_VERSION
  gem 'web-console'
  gem 'listen', '~> 3.1.0'
  gem 'spring'
  gem 'spring-watcher-listen', '~> 2.0.0'
  gem 'letter_opener_web', '~> 1.3.0'
end
