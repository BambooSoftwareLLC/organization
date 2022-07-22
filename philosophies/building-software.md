# Building Software

Maximizing value... the 80/20 principle... whatever you want to call it...

Bamboo prefers a pragmatic approach to building software for clients: _software is a tool for the client's business, not the end-goal in itself_ (even for software companies!).

## Highlights

- Prefer simplicity over complexity
- Prefer broad acceptance tests over fine-grained unit tests, but ALWAYS incorporate tests
- Prefer native constructs over custom solutions
- Prefer popular packages over cool ones

## Prefer simplicity

Software development is hard. It's complex. It's confusing.

As software craftsmen, we shouldn't add to the complexity.

"We write code first for humans, and then for computers."

Simple code is readable code. Simple code is maintainable code. Simple code is changeable code. Simple code is valuable code.

### Simpler components

Don't use a complex component that's hard to use when a simpler one exists that does 80%+ of what you need it to do.

If clients ask for specific features that would require not using a simple component, push back. Tell them how much more the custom or complex component would cost to implement. We're the software experts, so we need to be responsible for telling them what they need to know in order to make responsible business decisions.

Forgoing an edge case because the development effort is exponentially higher than the simple case could be a valid business decision, so they need to be made aware of the context to empower them to make the ultimate decision.

### Simpler architecture

Don't use complicated architecture when simplicity will do.

- Prefer monoliths over microservices, even for APIs that need infinite horizontal scaling (containers + Cloud Run > separate cloud functions).
- Prefer scheduled jobs over real-time triggered jobs.
- Prefer easy deployments over complex deployments

When choosing the more complicated architecture, our decisions MUST be backed up with a clear reason why the simpler alternative just won't due.

### Simpler workflow

How is new code incorporated into deployed products? What hoops need to be jumped through? What needs to happen in order to begin working on a new feature?

- Use simple processes when building new features. Ask the client for input, refine it, get rough sign-off, and start working. We don't need to ritualize everything.
- Simplify deploying new features. Versioning should be easy. Deployments to various environments should be easy. We're software people... automate this stuff! (This is an example of "complex architecture" colliding with "simple workflows"... do the best you can with your expert judgement)
- Use workflows that already exist, and that people already know.

### Simpler algorithm

Remember, we write code for humans. Make it simple first. If we need to performance tune later, we can do that then.

## Prefer broad acceptance tests

Tests are necessary.

Tests should provide assurance to everybody involved with a software project that the code does what we think it does.

Software usually has a limited number of public ports, the parts that ultimately show up to end users. These are the only points really worth testing. This provides the greatest freedom to refactor (for performance, readability, etc.) with assurance that we won't break anything that ultimately matters. This also limits the number of tests we need to write, and it's the easiest for the business stakeholders to contribute to test cases.

Sometimes, the end users are other developers... sometimes even ourselves. In these cases, our tests might look like unit tests, but they're still ultimately broad acceptance tests.

If bugs are found, practice TDD. This is the only reliable way to continually improve the quality of the software.

## Prefer native constructs

When the language/framework does something and a third-party package does the same thing, or roughly the same thing, prefer using the native language/framework implementations.

- The native implementations are probably higher quality code.
- They're also more likely to be supported into the future.
- They're also more likely to have examples for usage on StackOverflow (**very important!**).

## Prefer popular packages

Similar to native implementations, when we have to use third-party packages (or frameworks/languages themselves), prefer the more popular ones. Maybe the less popular one will be ubiquitous one day, but it's not now.

With more popular packages, we gain the same benefits as using native implementations: higher quality, more future-proof, more documentation.
