# Code Review: For Me & You

On the surface, the idea of code review is a no-brainer: why *wouldn't* we want a second set of eyes on our code, especially before deploying to production?

As we peel back the layers, however, we find that the topic of code review is much more nuanced. How detailed should the review be? Who is qualified to perform the review (hint: it's not just senior developers)? Can we afford to take another developer away from their project to review this one? What steps can we take to ensure reviews are constructive, rather than demoralizing?

Attendees will gain deeper insight into some of the arguments for and against systemic, peer code review, as well as pick up some useful tools to make code review a natural part of their teams' workflow.

:sparkles: **[View slides](http://stevegrunwell.github.io/code-review-for-me-and-you)** :sparkles:

## Presentation History

* [PHP Tek 2025](https://phptek.io/) — May 22, 2025 ([PDF](https://github.com/stevegrunwell/code-review-for-me-and-you/releases/download/php-tek-2025/slides.pdf), [Joind.in](https://joind.in/talk/02c73))
* [Cascadia PHP 2019](https://2019.cascadiaphp.com/) — September 20, 2019 ([PDF](https://github.com/stevegrunwell/code-review-for-me-and-you/releases/download/cascadia-php-2019/slides.pdf), [Joind.in](https://joind.in/talk/bcbbb))
* [Beer City Code 2019](https://beercitycode.com/) — June 1, 2019 ([PDF](https://github.com/stevegrunwell/code-review-for-me-and-you/releases/download/beer-city-code/slides.pdf))
* [php[world] 2018](https://2018.world.phparch.com/) — November 14, 2018 ([Joind.in](https://joind.in/talk/f22e0), [PDF](https://github.com/stevegrunwell/code-review-for-me-and-you/releases/download/phpworld-2018/slides.pdf))
* [Cascadia PHP 2018](https://2018.cascadiaphp.com/) — September 15, 2018 ([Joind.in](https://joind.in/talk/9f157), [PDF](https://github.com/stevegrunwell/code-review-for-me-and-you/releases/download/cascadia-php/slides.pdf))
* [INN Labs Office Hours](https://stevegrunwell.com/speaking/inn-labs-office-hours-may-25-2018/) — May 25, 2018 ([Video](https://youtu.be/4uuRuDm8oJo), [PDF](https://github.com/stevegrunwell/code-review-for-me-and-you/releases/download/inn-office-hours/slides.pdf))
* [WordCamp Dayton 2018](https://2018.dayton.wordcamp.org/) — May 19, 2018 ([PDF](https://github.com/stevegrunwell/code-review-for-me-and-you/releases/download/wordcamp-dayton-2018/slides.pdf))

## Resources

Below are links to some of the tools referenced throughout the talk.

### Linting & Static Code Analysis Tools

* [PHP_CodeSniffer](https://github.com/PHPCSStandards/PHP_CodeSniffer/) — Extremely popular linter (and fixer) for PHP
* [PHP Coding Standards Fixer](https://github.com/PHP-CS-Fixer/PHP-CS-Fixer) — Alternative to PHP_CodeSniffer from the Symfony ecosystem
* [PHPStan](https://phpstan.org) - A very popular—and dare I say the best?—static code analysis tool for PHP
* [Psalm](https://psalm.dev/) - Another popular PHP static code analysis tool (from Vimeo)
* [ESLint](https://eslint.org/) - Prominent linter for the JavaScript ecosystem
* [Shellcheck](https://www.shellcheck.net/) - Shell script analysis tool
* [RuboCop](https://rubocop.org/) - Linter/formatter for Ruby
* [PyLint](https://www.pylint.org/) - Linter for Python code

### Git Hooks

* [Husky](https://github.com/typicode/husky) - Tool that can automatically install Git hooks in your local repo
* [Lefthook](https://github.com/evilmartians/lefthook) - Alternative to Husky, written in Go
