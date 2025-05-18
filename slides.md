<!-- .slide: class="title-slide" data-hide-footer -->
# Code Review:<br>For Me &amp; You

Steve Grunwell <!-- .element: class="byline" -->
[@stevegrunwell@phpc.social](https://phpc.social/@stevegrunwell)
[stevegrunwell.com/slides/code-review](https://stevegrunwell.com/slides/code-review)

---

##  What is Code Review?

Note:

Before I can tell you all the reasons you should be doing code review, it's important to understand what the term means.

Code review can take a few different forms:

----

### Formal code review

* <!-- .element: class="fragment" --> An <u>official</u> part of your development workflow
* <!-- .element: class="fragment" --> Development &rsaquo; Code Review &rsaquo; Merge
* <!-- .element: class="fragment" --> "Bug sweeps"

Note:

* An official part of team's development workflow
* Every (major) change gets reviewed before merge
    - Pair programming? Essentially already doing this!
* Bug sweeps = larger chunks are reviewed after merging
    - "post-mortem code review" (better late than never?)

----

### Informal code review

* <!-- .element: class="fragment" --> Not (just) workflow, but culture
* <!-- .element: class="fragment" --> Ad-hoc check-ins
* <!-- .element: class="fragment" --> "Hey, can you gut-check this?"

Note:

* Not required, but rather a part of your team culture
    - Can actually be some of the best learning opportunities
* Over-the-shoulder checks or poking around commit history on GitHub
* Requires a culture of respect; competitive types need not apply

---

## The Value of Code Review

Note:

While it may be immediately apparent to some, regular code review carries a lot of value that some teams don't recognize until they've been at it for some time.

----

### "Shift Left"

> The earlier you can catch issues, the less expensive they'll be to fix

Note:

* A general theme you'll see emerge through this talk is "shift left"
    - Corporate speak for "it's easier to fix things when we catch them early than it is after they've hit production"
* The more we can do to catch these issues early via code review, automated testing, etc. the faster we can resolve issues

----

<!-- .slide: data-hide-footer data-background="resources/ash-meme.png" data-background-size="contain" data-background-position="center center" -->

Note:

* Two sets of eyes are better than one!

----

### Catch Bugs

* A second set of eyes on the code
* <!-- .element: class="fragment" --> Are assumptions about the requirements correct?
* <!-- .element: class="fragment" --> Missing corner cases, tests, etc.
* <!-- .element: class="fragment" --> Are there cleaner ways to do this?

Note:

* Sometimes it just takes a second person to notice "hey, this function isn't doing what it's supposed to"
* Catch corner-cases, missing tests, sanitization and escaping issues, etc.
* General suggestions to improve code quality
    - Some of this can be automated, more on this later

----

### Catch larger architectural issues

* <!-- .element: class="fragment" --> Requires more ramp-up
* <!-- .element: class="fragment" --> The first line of defense against technical debt

Note:

* Code review can also help expose larger architectural issues
* Requires a better understanding of the codebase
    - Do we already have logic elsewhere to handle this that we're duplicating?
    - Are we fighting against the framework?
    - Will this work with production traffic?
    - Are there security concerns (SQL injection, input sanitization, etc.)?
    - Are we reinventing the wheel?
* Code review == your first line of defense against technical debt

----

### Reduce the Bus Factor&trade;

**noun | bəs fak-tər**

_How many folks can you lose<br>before you're utterly screwed?_

Note:

* The "bus factor" (see also: "Lottery Factor") is basically the number of key individuals the project depends upon
* If only two people understand how it all works and they get hit by a bus, win the lottery, retire, or get burned out and quit, that's a bus factor of 2.
* Mitigate this risk by breaking down these knowledge silos; code review is a great way to build a shared understanding

----

### Developer growth

* <!-- .element: class="fragment" --> Great way to help junior developers grow
* <!-- .element: class="fragment" --> Great way to help <strong>senior</strong> developers grow

Note:

* Great way to help developers continue to learn + grow
* Seniors reviewing juniors = mentorship opportunity and real, actionable feedback
* Reviewing seniors keeps them up-to-date
    - Yesterday's best practice is tomorrow's anti-pattern
    - Include juniors: great learning opportunity and extra insight is helpful

----

#### Who should perform code review?

![Everyone!!!](resources/everyone.gif)

Note:

* Too much to be gained through review to limit it to seniors reviewing juniors
* No two devs have the same experience, outside perspective FTW
* Review shows reviewer the thought process, which is insight into the developer's mind

----

### Common arguments<br><u>against</u> code review

* <!-- .element: class="fragment" --> Ain't nobody got time for that!
* <!-- .element: class="fragment" --> I reviewed it and can confirm that it is,<br>in fact, code.
* <!-- .element: class="fragment" --> Death by a thousand paper-cuts

Note:

* Good code review takes time
    - Larger the review, the more uninterrupted time needed
    - Make the time to catch bugs now or let the them ruin your weekend when prod goes down: your choice!
* If the code's not earnestly being reviewed, it's a charade and a waste of time
    - Far less-costly to catch bugs before they hit prod, but you do you, I guess?
    - "We've tried nothing and we're all out of ideas!"
* Conversely, some people get *too* into reviews, and it becomes nitpicky and unhelpful
    - e.g. "That's not how _I_ would have done it!"
    - This is a people problem, not an issue with code review.

----

> The goal of code review is to—as a team—arrive at the best possible solution to a problem.

Note:

Remember: the goal of code review isn't to make things perfect, but to put smart people together to determine the best possible solution to a problem.

----

### Building a Culture of Code Review

* <!-- .element: class="fragment" --> Make code review an integral part of your team's workflow
* <!-- .element: class="fragment" --> Empower every member of your team to request a review
* <!-- .element: class="fragment" --> If it's not important enough to review, it's not important enough to ship!

Note:

* Best way to ensure code reviews get done is to make them a part of the workflow.
    - Reviews are not a "sometimes" thing, they are a required step
* Everyone should be able to request a review, and should feel empowered to jump into one, too
    - Great learning opportunity, and the more eyes the better
* No shortcuts; hotfixes mean emergency code reviews, not skipping the process entirely.

----

<!-- .slide: data-background-image="resources/pacino-godfather.jpg" data-background-size="cover" data-background-position="center top" data-hide-footer -->

It's not personal,<br>it's strictly business.
<!-- .element: class="meme-text" -->

Note:

* Remember that code reviews are meant to help you improve your code and grow as a developer; they are *not* meant to be personal attacks on a developer's skills
* As tempted as you may be, don't take—or make—reviews personal

----

<!-- .slide: data-background-image="resources/let-it-go.png" data-background-position="center center" data-background-size="cover" data-hide-footer -->

Code Ownership:<br>Let it Go!
<!-- .element: class="meme-text" -->

Note:

* It is not your code, it is the team's code!
* When you're being reviewed, it's easy to feel attacked
* Also easy to feel like someone's trying to rewrite your baby
* Code review is a compromise, moving towards the best possible solution

----

### Code Review Priorities

1. <!-- .element: class="fragment" --> Does it work?
2. <!-- .element: class="fragment" --> Does it work well?
3. <!-- .element: class="fragment" --> Does it meet our standards?

Note:

Prioritize feedback:

1. Does the code do what it's designed to do, and/or does it break anything else?
2. Are there potential security/performance issues (escaping, sanitization, etc.)
3. Does it adhere to the coding standards and other rules?

---

## Facilitating Code Reviews

Note:

If we can agree that there's worthwhile value to be had from regular code review, let's walk through what a typical code review looks like:

----

### GitHub Pull Requests

1. <!-- .element: class="fragment" --> Push new branch
2. <!-- .element: class="fragment" --> Open a pull request (PR)
3. <!-- .element: class="fragment" --> (Optional) CI pipeline
4. <!-- .element: class="fragment" --> Reviewer(s) leave feedback
5. <!-- .element: class="fragment" --> Merge!

Note:

* A very popular way to handle code reviews is via Pull Requests on a tool like GitHub
* General workflow: make change in branch, open PR, maybe run CI, reviewer(s) leave feedback, then merge

----

#### Push your branch

```sh
$ git checkout -b fix/moar-pet-photos
Switched to a new branch 'fix/moar-pet-photos'

# Make your changes + commit

$ git push -u origin fix/moar-pet-photos
```

Note:

* All new work will be done in a branch
* You may certainly use a GUI if you prefer

----

<!-- .slide: data-background-image="resources/compare-branches.png" data-background-size="100% auto" data-background-position="center top" data-background-color="#fff" data-hide-footer -->

Note:

* A PR consists of one branch compared to a base branch
    - Branches can also exist across forks on GitHub
* Typically, branches will be merged into "main" or "develop" (varies by workflow)
* Review the changes, then click "Create pull request" to get text editor to provide a descriptive title + description of the changes

----

<!-- .slide: data-background-image="resources/pr-body.png" data-background-size="100% auto" data-background-position="center top" data-background-color="#fff" data-hide-footer -->

Note:

* Here's a PR on GitHub
* Base and feature branch, and a breakdown of commits
* Specific files that have changed

----

#### 3. (Optional) Execute CI pipeline

* <!-- .element: class="fragment" --> Run automated test suites
* <!-- .element: class="fragment" --> Check coding standards
* <!-- .element: class="fragment" --> Static code analysis
* <!-- .element: class="fragment" --> Calculate code coverage

Note:

* This step is optional, but can be a huge time saver!
* Anything you can do to catch low-hanging fruit here will save you time going back-and-forth
    - More on some of these suggestions in a bit!

----

<!-- .slide: data-background-image="resources/review-changes.png" data-background-size="100% auto" data-background-position="center top" data-background-color="#fff" data-hide-footer -->

Note:

* When I go to provide a review, I can explicitly approve, request changes, or simply comment
* See a diff of everything that's changed by file
* Let's say I want to comment on a line-by-line basis...

----

<!-- .slide: data-background-image="resources/inline-comment.png" data-background-size="100% auto" data-background-position="center top" data-background-color="#fff" data-hide-footer -->

Note:

* Dismiss the dialog and click a line number to leave inline feedback
    - Full markdown support
    - Add a single comment or start a review, which will batch the notifications
    - Each comment becomes its own threaded discussion
* When I'm done, click "Review Changes" to return to the approve/request changes/comment dialog.

----

### Other popular tools

* Codeberg
* Gitea
* GitBucket
* GitLab
* AWS CodeCommit
* Beanstalk
* Bitbucket
* Crucible

<!-- .element: class="two-column" -->

Note:

Many of the popular code review tools are tied into the repository host itself; Bitbucket, GitLab, and Beanstalk are all competitors to GitHub.

Meanwhile, Codeberg, Gitea, GitBucket, et al are self-hosted alternatives.

----

### Animal break! <!-- .element: class="screen-reader-text" -->

<div class="animal-break">
    <img src="resources/taco.jpg" alt="Taco, a black cat, wearing a witch hat that he totally didn't then proceed to destroy">
    <img src="resources/jolene.jpg" alt="Jolene, a black Labrador retriever, looking oh-so happy">
</div>

---

## Providing Feedback

----

### Be Objective, not Subjective

* <!-- .element: class="fragment" --> Put aside personal feelings and opinions, and try to provide objective feedback
* <!-- .element: class="fragment" --> Provide resources (where appropriate)
* <!-- .element: class="fragment" --> Ask questions!

Note:

* Important to put aside "that's not how I would do it" and instead focus on providing objective feedback
* Instead of citing "best practices", link to relevant docs
    - Gives your feedback authority, while giving the recipient a place to start
* If something doesn't make sense, ask the developer _why_ the approached it a certain way
    - Forces the dev to re-evaluate
    - The most important question you can ask is "WHY?"

----

👎 **Not so great:**

> If I were you, I'd move this function into the `Widget` class so it's not so hard to find.
<!-- .element: class="speech-bubble" -->

**Better:** <!-- .element: class="fragment" data-fragment-index="0" -->

> It seems like this function is closely related to the `Widget` class and not used anywhere else—would it make sense to move it into the class, instead?

<!-- .element: class="speech-bubble fragment" data-fragment-index="0" -->

Note:

* Instead of taking a "I know better than you" standpoint, make a statement and ask a leading question.

----

**Not so great:**

> Output should be escaped
<!-- .element: class="speech-bubble" -->

**Better:** <!-- .element: class="fragment" data-fragment-index="0" -->

> The output of this HTML attribute should be escaped via [`esc_attr()`](https://developer.wordpress.org/reference/functions/esc_attr/).
<!-- .element: class="speech-bubble fragment" data-fragment-index="0" -->

Note:

* If you're referencing a specific function or library, it can be helpful to provide a link to the relevant docs
* Supports your case + gives dev more background
    - Could lead the dev to read more about sanitization and late-escaping in WP

----

### Highlight Successes

Celebrate the small victories!

<blockquote class="speech-bubble fragment-replace fragment" data-fragment-index="0" style="margin-top: 1em;">
    <p class="fragment fade-in-then-out" data-fragment-index="0">Great catch, a lot of people would have missed that condition!</p>
    <p class="fragment fade-in-then-out" data-fragment-index="1">Where did you learn about this function? It's super useful!</p>
    <p class="fragment fade-in-then-out" data-fragment-index="2">You've really come a long way in your use of caching, well done!</p>
    <p class="fragment fade-in-then-out" data-fragment-index="3">This documentation is excellent,<br>thank you!</p>
</blockquote>

Note:

* Code reviews aren't just about what was done wrong, but encouraging what was done right, too
    - Especially important if you're reviewing code for a more junior developer
    - Support good habits and as well as highlighting problem areas

---

## Code Review, minus the "ew"

Note:

I've teased CI as a way to make code reviews easier a couple times, let's dig in!

----

### Let CI be the "bad guy"

The more quality checks that we can automate, the more time we have focus on the important aspects of code review!

Note:

* Big proponent of letting CI be the villain, as it frees reviewers up to focus on the "does it work?" and does it work well?" priorities
* You set the rules, and CI makes sure everyone follows them
* Another example of "shift left"

----

### The value of coding standards

* <!-- .element: class="fragment" --> Determine coding standards at the beginning of the project
    * PER 2.0 v. PSR-12 v. PEAR v. ¯\\\_(ツ)_/¯
* <!-- .element: class="fragment" --> Reduces merge conflicts, back-and-forth
* <!-- .element: class="fragment" --> Enforce standards via tooling

Note:

* Coding standards are a way of saying "this is how we write our code"
    - Tabs vs spaces, class + variable naming conventions, project file structure, etc.
* Consistent standards => fewer merge conflicts and a more readable codebase
* Once standards are determined, use tooling to ensure compliance

----

### Linting

* <!-- .element: class="fragment" --> Validate against project coding standards
    * <!-- .element: class="fragment" --> PHP_CodeSniffer, PHP Coding Standards Fixer
    * <!-- .element: class="fragment" --> ESLint, Shellcheck, RuboCop, PyLint
* <!-- .element: class="fragment" --> Highly-configurable, with reasonable defaults
* <!-- .element: class="fragment" --> Often capable of automatically fixing some issues!

Note:

* We can enforce coding standards with linting tools
    - In the PHP ecosystem, most popular are PHP_CodeSniffer and PHP Coding Standards Fixer
    - Similar tools across languages: JavaScript, Bash, Ruby, Python, etc.
* Generally offer rulesets for common standards, but can be customized for individual teams/projects
* Helps catch the low-hanging fruit: whitespace, naming schemes, syntax errors, missing documentation, undeclared variables, etc.
* Many include automated fixing tools (e.g. PHP Code Beautifier), which can fix a lot of common issues automatically

----

### .editorconfig

* <!-- .element: class="fragment" --> Standard for file encoding, whitespace, line endings, and more
* <!-- .element: class="fragment" --> Defaults available for most popular standards
* <!-- .element: class="fragment" --> <a href="https://editorconfig.org">editorconfig.org</a>

Note:

* Dotfile supported by most IDEs (sometimes requiring a plugin) that automatically configures the editor for things like file encoding, tabs v spaces, newlines vs carriage returns, etc.
    - Lives in repository, helps consistency
* Example files available for most popular standards

----

### Static code analysis

* <!-- .element: class="fragment" --> Examine the code without running it
* <!-- .element: class="fragment" --> Catch type issues, performance concerns, and more!
* <!-- .element: class="fragment" --> Great addition to—but not replacement for—code review

Note:

* Often sold as "automated code reviews"
    - More advanced than tools like ESLint or PHP_CodeSniffer, which are focused more on syntax
* Detects type issues, logical errors, performance concerns, and a lot more
    - Most can be extended with additional rulesets
* Great at assisting with the "does it work well?" priority of code reviews, but tools don't know everything!
* Examples: PHPStan, Psalm, Code Climate, Codacy

----

### "Can't AI Do It?"

* <!-- .element: class="fragment" --> "AI" tools can be used to <u>assist</u> in code review
* <!-- .element: class="fragment" --> Summarize changes, catch high-level errors
* <!-- .element: class="fragment" --> "Overly-confident generalist"
* <!-- .element: class="fragment" --> <u>You</u> are still responsible for signing-off!

Note:

* Not a fan, but we've started using an AI tool (Qodo Merge) on PRs at work.
    - To its credit, it does catch a fair amount of issues...that are already being caught by tools like PHPStan
* Main purpose is to catch syntax errors and make recommendations, but will likely need to be trained on your codebase.
* If you can catch these issues using more-specialized tools (e.g. static code analysis), trust those rather than AI
    - be wary of "magic" tools that claim to understand all languages!
* Most importantly, remember that these tools exist to _help_ with reviews, but you are still accountable for signing off on PRs. Don't make the mistake of thinking that the AI is always right (spoiler alert: it's not), do the work!

---

## Advice from the Trenches

Note:

To wrap up, I'd like to leave you with some of the most important things I've learned in my years of doing code review.

----

### Practice Atomic Commits

* <!-- .element: class="fragment" --> Make each commit as small & focused as possible
* <!-- .element: class="fragment" --> Commits are cheap, go wild!

Note:

* Each commit should be small and focused, touching as little as possible
* Branching and commits are cheap, so commit early and often
* Way easier to see what's changed, why it changed, and make reverts far less painful

----

###  Atomic Commits

```sh
$ git commit -am "#YOLO" && git push --force
```

![Krysten Ritter proclaiming "Oh, I just realized. I hate you"](resources/i-hate-you.gif)<!-- .element: class="fragment" -->

Note:

Meanwhile, this is the opposite of an atomic commit.

Please don't be the person who does this kind of thing, or you're going to be the team member that nobody wants to work with.

----

###  Atomic PRs

* <!-- .element: class="fragment" --> PRs should be as small & focused as possible
* <!-- .element: class="fragment" --> Smaller PRs == shorter feedback loop
* <!-- .element: class="fragment" --> Avoid a CODEOWNER stampede

Note:

* PRs should be as small as (reasonably) possible
    - Big difference in cognitive load between ten small PRs with a few changes each v. one giant PR
* Smaller PRs lead to faster reviews
    - Easier to grab between tasks
    - More likely to get done in a reasonable amount of time
* If you rely on CODEOWNERS, try to minimize the number of teams that require sign-off

----

### Draft PRs

* <!-- .element: class="fragment" --> Not-ready-for-Primetime
* <!-- .element: class="fragment" --> Opportunity to have discussions and on-going reviews
* <!-- .element: class="fragment" --> Keep notes related to a specific branch

Note:

* Most tools now offer the ability to create draft PRs, but previously the convention was labelling PRs a "WIP"
* Good for collecting preliminary feedback (e.g. "does this approach make sense"), ensuring CI passes, etc. without signaling that it's ready for a final review
* For more complicated branches (e.g. release prep), can help keep track of changes as you go

----

### Issue References

> This PR introduces X feature.
>
> Fixes #17, blocked by #42.

Note:

* Most platforms will allow you to reference other PRs or issues, which helps provide context
* Some key words (fixes, closes, etc.) will actually automatically close the referenced issues once the PR is merged
* It's also not uncommon for PRs to depend on other PRs being merged first
    - Adopting a convention of "blocked by X" helps teammates see where these dependencies are (even if tools won't automatically block a PR from being merged)

----

### Embrace the .gitignore

A versioned file that excludes files from the repo

```sh
# Exclude these files from the repo:

node_modules/
vendor/
*.log
*.sql
```

Note:

* Exclude code loaded via dependencies (node_modules, vendor, etc.)
* More code excluded == less code to be checked and reviewed
* Omit compiled assets if you're able to leverage build scripts or a CI/CD pipeline

----

### Git hooks

* <!-- .element: class="fragment" --> Enable you to execute scripts throughout the Git lifecycle
* <!-- .element: class="fragment" --> Not stored within the repo!
* <!-- .element: class="fragment" --> Analyze code before committing, perform actions ahead of a <code>git push</code>

Note:

* Scripts that can be executed throughout Git lifecycle
* Not stored in the repo by default, but can easily be distributed
    * Tools like Husky, Lefthook, etc. can handle setting these up automatically
* Things like automatically running PHP_Codesniffer pre-commit, updating dependencies on git pull, or running tests ahead of a git push

----

### Review documentation

* <!-- .element: class="fragment" --> Treat inline documentation as code
* <!-- .element: class="fragment" --> Reduces "Doc Rot"
* <!-- .element: class="fragment" --> Out-of-date docs? No merge for you!

Note:

* When performing code reviews, be sure to review relevant documentation along with the rest of the code
    - If a function's arguments or return value changes, the docs better be updated to match!
* Helps reduce "Doc Rot", when the documentation doesn't match the actual behavior
* If docs aren't being updated with the code, request changes in the PR
    - Do not let bad docs get merged!

----

### Audit your baselines

> If an app isn't working right but all the tests pass, the first place you should look are the areas where test coverage has been ignored!

Note:

* Most linters, static code analysis tools, etc. will allow errors to be suppressed
    - Often these suppressions are either inline (via comments) or in a "baseline" file
* Additionally, certain files can be omitted from code coverage calculations
* If you're running into bugs but everything that's being checked seems to be working as expected, double check that you're not accidentially suppressing an actual issue!

---

<!-- .slide: data-hide-footer -->

## Thank You!

Steve Grunwell<br>
<span style="font-size: .75em;">Staff Software Engineer, Mailchimp</span>

[stevegrunwell.com/slides/code-review](https://stevegrunwell.com/slides/code-review)<!-- .element: class="slides-link" -->
