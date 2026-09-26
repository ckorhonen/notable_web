# Repository guide

## Map and local work

This gem supplies a Rails dashboard for Notable. `app/controllers/notable_web/` and `app/views/` contain dashboard behavior; `lib/notable_web/` defines the engine/version; `config/routes.rb` holds routes. `README.md` documents mounting the engine, authentication, and Kaminari/will_paginate interoperability.

Use `bundle install` with `Gemfile`/`notable_web.gemspec`. Development dependencies specify Bundler ~> 1.7 and Rake ~> 10.0; no Ruby pin or lockfile is tracked. `bundle exec rake build` packages the gem; the Rakefile contains only Bundler gem tasks, with no test/lint/server command or tracked test suite/CI. For changed Ruby files use `ruby -c path/to/file.rb`; validate dashboard behavior in a disposable compatible Rails host with synthetic Notable records and add focused regression coverage where practical.

Keep dashboard authentication intact and preserve the documented pagination compatibility option. Do not use real event histories, accounts, or production databases as test data. A host app is required for browser verification; syntax checks alone do not prove route/auth/rendering behavior.

## Completion and boundaries

Start with `git status --short` and preserve unrelated edits. Carry authorized local changes through relevant checks and repairs, choosing ordinary reversible details directly. Live database/account changes and gem publication require explicit task authorization. If legacy dependencies or the host fixture are unavailable, state the exact blocker and continue independent checks. Prose-only edits need source/link inspection and `git diff --check`; report changed paths, actual checks/results, and remaining integration gaps.
