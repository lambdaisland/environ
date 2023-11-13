This is a fork of the
[weavejester/environ](https://github.com/weavejester/environ) library. It
exposes the same core namespace and API (`environ.core`), but with different
behavior.

- no lein-environ / `.lein-environ`
- no boot-environ / `.boot-environ`
- read a `.env` file from the project root, parsed using `lambdaisland/dotenv` (so variable expansion is available), and merged in last (so it always takes precendence), without warning about overriding keys (because its main use case is for intentional local overrides)

This fork came into existence because the Gaiwan team inherited a client project
that was using Environ, and found it frustrating that Environ lacks a good
mechanism for managing local overrides, especially in combination with
cider-jack-in, where it's not obvious where changes to the environment should be
configured.

We generally don't recommend using Environ, and certainly don't recommend using
this branch, unless in the very specific scenario where you have an existing
application you need to support, and find the behavior of having a local `.env`
for overrides a helpful stopgap while you transition to a different solution.

You SHOULD NOT depend on this library from other libraries.
