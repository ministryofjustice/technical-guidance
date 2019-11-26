---
category: Development Principles
expires: 2019-03-31
---

# Development Principles

These principles are stated in no particular order, and are *always* open to debate.
All development is a trade-off between competing pressures, these principles are
meant to help you decide which trade-offs are acceptable.

They are guidance, not The Law - there will always be edge cases, but you should
expect to be challenged if you go your own way. The principles are to guide future
and current development - use your judgement, but in general only rewrite existing
code if you really have to.

## General Principles

### 1. Share the knowledge

If you have knowledge which is unique to you, it is your responsibility to share it.

We follow '[github flow](https://guides.github.com/introduction/flow/)', to keep branches small and short-lived, and ensure knowledge is shared.
If you produce something reusable, package it (e.g. with [PyPI](https://pypi.org) or [rubygems](https://rubygems.org)) & share it with others on [MoJ Reuseables]( https://github.com/ministryofjustice/moj-reusables).

All non-throwaway code should be reviewed - no-one is 100% right, 100% of the time... Be aware that 'throwaway' code has a nasty habit of sticking around.

### 2. Code should be correct, clear, concise - in that order

Correct means provably correct - with tests. All fixes & new features should include tests to prevent regressions.

Choose clarity over cleverness - avoid monkey-patching and meta-programming unless you have a very good reason not to.

Don't Repeat Yourself - The '[Rule of Three](https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming))' is a good approach to managing duplication. Less code is usually better - but not at the expense of clarity.

### 3. Optimize for change

Don't try to solve every conceivable problem up-front, instead focus on making your code easy to change when needed.

Don't prematurely optimize - choose clarity over performance, unless there is a serious performance issue that needs to be addressed.

### 4. Something simple which exists is better than a perfect solution which doesn't exist yet

We learn best from putting real things in front of real users, not trying to achieve perfection in isolation.
There is no substitute for a real user clicking through a user journey in a real application. Get it done, get it in front of people, and learn early.

Don't over-engineer. Follow the principle of Least Surprise. Choose process
concurrency over threading & let the O/S handle it, unless there is good reason.
When you do use threading, use language abstractions to help. Don't roll your
own crypto. Handle exceptions at the app level, no lower, etc.

### 5. Everything fails, all of the time.

Accept this and [code defensively](https://en.wikipedia.org/wiki/Defensive_programming) when calling other services.

Every HTTP call could error or hang - handle failures appropriately and fail fast. Don't let long-running external
calls impact your user experience.

### 6. Other developers are users too - treat them with respect

If you have to explain how your code works, then your code is not clear enough.
Comments are for explaining **why** something is needed, not how it works.

Commit messages should follow [GDS guidance](https://github.com/alphagov/styleguides/blob/master/git.md)
No-one cares how clever you are - it's far more important to work well with your team.

APIs are interfaces too - Like any other interface, APIs need designing and iterating for usability.

Don't pollute the global namespace.

### 7. Think smaller

Stick to the Single Responsibility Principle - keep view templates, controllers and model classes as simple
as possible. Keep methods short. Concepts and patterns which may help with this: Null Object pattern, 
Facade pattern, Form Objects, Sandi Metz's '[Rules for Developers](https://robots.thoughtbot.com/sandi-metz-rules-for-developers)'.

A solution composed of many small simple things is usually better than one big complex thing.

### 8. Names have power. Use them wisely

Don't be cute or jokey when naming things. Names convey meaning - well-named functions & variables can 
remove the need for a comment. Avoid meaningless names like `obj` / `result` / `foo`.

Use single-letter variables only where the letter represents a well-known mathematical property
(e.g. e = mc^2), or where their meaning is otherwise clear.

See [Naming things]({{ 'standards/naming-things' | relative_url  }}).

### 9. Composition over inheritance

It's tempting to build an inheritance tree of objects extending others and redefining methods where needed -
but that often just creates tech debt for the future. Choose 'has-a' relationships over 'is-a' - e.g. a
Car has-a Motor, rather than Car is-a MotorVehicle.

### 10. Any attempt to predict the future is likely to be wrong

This includes estimates of work - if they are to be used for assigning budget or predicting delivery dates,
they should always come with a level of confidence, or a best/worst case range (e.g. "between x and y days"
or "maybe x days, but i'm only 50% confident of that").

The larger the chunk of work you're estimating, the more inaccurate you will be - so if it doesn't fit into
a single sprint, break it down until it does.

## Ruby-specific principles

### 1. Handle exceptions at the application level, not component level

(*This differs slightly from the Python principle in wording and philosophy*)

Don't swallow exceptions in your libraries, let them propagate up to the application.
It's usually only there that sufficient context exists to decide upon the appropriate action.

Exceptions are for the unexpected & unhandleable, not flow control.

Always put specific exception types in rescue statements (unless you have good reason not to).

### 2. Use meta-programming with extreme caution

Unless done very carefully, meta-programming makes code harder to read, debug, and understand.
It also creates performance issues through purging method caches, etc. Just because you can meta-program
in Ruby, doesn't mean you should  - there's nearly always a better way.

## Python-specific principles

### 1. Handle exceptions at the application level, not component level

(*This differs slightly from the related Ruby-specific principle in wording and philosophy*)

Don't swallow unexpected open type or base type exceptions in your libraries, let them propagate up 
to the application. It's usually only there that sufficient context exists to decide upon the 
appropriate action. Always specify an exception type in a try/except unless there is a good reason not to.

### 2. PEP 8

Always try to follow [pep8 code style](https://www.python.org/dev/peps/pep-0008/) and
consider the [Zen of Python](https://www.python.org/dev/peps/pep-0020/).
