# FORUM.SOMENERGIA.COOP

## Deploying the app

Deployed with [Capistrano](http://capistranorb.com/) using [Figaro](https://github.com/laserlemon/figaro) for `ENV` configuration.

```bash
cap integration deploy
```

## Setting up the application

You will need to do some steps before having the app working properly once you've deployed it:

1. Open a Rails console in the server: `bundle exec rails console`
2. Create a System Admin user:
```ruby
user = Decidim::System::Admin.new(email: <email>, password: <password>, password_confirmation: <password>)
user.save!
```
3. Visit `<your app url>/system` and login with your system admin credentials
4. Create a new organization. Check the locales you want to use for that organization, and select a default locale.
5. Set the correct default host for the organization, otherwise the app will not work properly. Note that you need to include any subdomain you might be using.
6. Fill the rest of the form and submit it.

You're good to go!


## Thinks to keep in mind for future upgrades.

Forum SomEnergia has some customizations.
One of this customizations, add badges to users and needs a dependency with gem `decidim-cas_client`.

- If user is verified with CAS CLIENT it has one badge.
- If user is an admin, it has a different badge.  

Take into account that this customizations are overwritting some decidim files.
These are the files overwritted:

- Cells:
  - `app/cells/decidim/author/profile_inline.erb`
  - `app/cells/decidim/profile_sidebar/show.erb`
  - `app/cells/decidim/user_profile/header.erb`

- Presentes:
  - `app/presenters/decidim/debates/official_author_presenter.rb`
  - `app/presenters/decidim/proposals/official_author_presenter.rb`
  - `app/presenters/decidim/user_group_presenter.rb`  
