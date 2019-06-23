# Porting Scala 2 – to Dotty (OS-Lib Compilation example)
The following issues encountered when compiling OS-Lib under Dotty:

## Scalafix candidates
- If a method is defined `toSet()`, it cannot be called `toSet`.
- “result type of implicit definition needs to be given explicitly”
- There are no `'Symbols` in Scala 3

## Trivial
- Acyclic is a compiler plugin, so obviously unavailable.asa
- Scala 2.13 libraries cannot be used from Dotty, because the type signatures have Scala version `5.3` but `5.0` is expected.
- `geny`, `utest` and `sourcecode` are dependencies of the lib. We explicitly declare them as `_2.12` to use from Dotty.
- Feature warnings about implicits `scala.language.implicitConversions` are output by default, unlike in Scala 2. This creates noise. Unclear how to turn off.
- Implicit conversions must be applied explicitly: `s.foldLeft(rel){_ / conv(_)} // conv: T => RelPath`

## Tricky
- Haoyi uses macros all over the place in his  test framework. Scala 3 doesn’t support them.