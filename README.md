# GantSign Checkstyle Configuration

[![Validation](https://github.com/gantsign/checkstyle-config/workflows/Tests/badge.svg)](https://github.com/gantsign/checkstyle-config/actions?query=workflow%3AValidation)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Checkstyle configuration for Java code written by GantSign.

## Severity Level

The default severity level is `error`; the goal is to ensure quality rather than
suggest it.

## @SuppressWarnings Support

Because the rules are quite strict `@SuppressWarnings` can be used to suppress
errors where necessary. It is the responsibility of the code reviewer to judge
whether suppression of the rule is the appropriate solution.

## Google Java Style Guide compatibility

Gantsign rules are based on the Google Java Style Guide
[Checkstyle rules](https://github.com/checkstyle/checkstyle/blob/master/src/main/resources/google_checks.xml).
It's recommended that your source code be automatically formated as part of
your build. You can find formatting tools at
[https://github.com/google/google-java-format](https://github.com/google/google-java-format)).

Any file compliant with these rules is compliant with Google Java Style Guide
Checkstyle rules. The reverse isn't necessarily true as the GantSign rules
include some additional checks.

## Additional rules for GantSign's code

* [DeclarationOrder](http://checkstyle.sourceforge.net/config_coding.html#DeclarationOrder)

    * Declaration order: enforce declarations appear in the following order:

        1. Class (`static`) variables. First the `public` class variables,
           then `protected`, then package level (no access modifier), and then
           `private`.
        2. Instance variables. First the `public` class variables, then
           `protected`, then package level (no access modifier), and then
           `private`.
        3. Constructors
        4. Methods

* [RedundantModifier](http://checkstyle.sourceforge.net/config_modifier.html#RedundantModifier)

    * Modifiers: ban redundant modifiers (e.g. public for methods in an
      interface).

* [RedundantImport](http://checkstyle.sourceforge.net/config_imports.html#RedundantImport)

    * Imports: ban redundant imports.

* [MissingDeprecated](http://checkstyle.sourceforge.net/config_annotation.html#MissingDeprecated)

    * Deprecated: require `@Deprecated` annotation and `@deprecated` JavaDoc tag
      if either are present.

* [MissingOverride](http://checkstyle.sourceforge.net/config_annotation.html#MissingOverride)

    * Override: require `@Overrides` annotation if `@inheritDoc` JavaDoc tag is
      present.

* [PackageAnnotation](http://checkstyle.sourceforge.net/config_annotation.html#PackageAnnotation)

    * Package annotations: ensure package annotations are only used in the
      `package-info.java` file.

* [InterfaceIsType](http://checkstyle.sourceforge.net/config_design.html#InterfaceIsType)

    * Interfaces: make sure interfaces contain methods and not just constants;
      no more interfaces like `javax.swing.SwingConstants`.

* [CovariantEquals](http://checkstyle.sourceforge.net/config_coding.html#CovariantEquals)

    * Equals: if you define your own type-specific equals method e.g.
      `Person.equals(Person)`, you must also override the default equals method
      e.g. `Person.equals(Object)`.

* [EqualsHashCode](http://checkstyle.sourceforge.net/config_coding.html#EqualsHashCode)

    * HashCode: if you override `equals()` you must also override `hashCode()`.

* [MagicNumber](http://checkstyle.sourceforge.net/config_coding.html#MagicNumber)

    * Numbers: ban magic numbers (i.e. numbers not defined with constants);
      sensible exclusions apply (e.g. array initializers).

* [SimplifyBooleanExpression](http://checkstyle.sourceforge.net/config_coding.html#SimplifyBooleanExpression)

    * Boolean logic: force obvious simplification of boolean logic:

      e.g.

      ```java
      if (booleanValue == true)
      ```

      should be:

      ```java
      if (booleanValue)
      ```

* [SimplifyBooleanReturn](http://checkstyle.sourceforge.net/config_coding.html#SimplifyBooleanReturn)

    * Boolean returns: ban unnecessary `if` `else` blocks for boolean returns:

      e.g.

      ```java
      if (booleanValue) {
          return true;
      } else {
          return false;
      }
      ```

      should be:

      ```java
      return booleanValue;
      ```

* [StringLiteralEquality](http://checkstyle.sourceforge.net/config_coding.html#StringLiteralEquality)

    * String: ban use of identity equals on strings literals.

* [ExplicitInitialization](http://checkstyle.sourceforge.net/config_coding.html#ExplicitInitialization)

    * Initialization: ban explicitly initializing fields to their default
      values.

* [IllegalInstantiation](http://checkstyle.sourceforge.net/config_coding.html#IllegalInstantiation)

    * Wrapper types: ban using constructor of wrapper types.

* [IllegalType](http://checkstyle.sourceforge.net/config_coding.html#IllegalType)

    * Collections: enforce using Collection interfaces for return types,
      parameter types and fields for basic collection implementation types.

* [MutableException](http://checkstyle.sourceforge.net/config_design.html#MutableException)

    * Exceptions: ban mutable exceptions; be aware this only checks the fields
      in the exception are declared final.

* [IllegalThrows](http://checkstyle.sourceforge.net/config_coding.html#IllegalThrows)

    * Exception handling: ban throwing `java.lang.Throwable`,
      `RuntimeException`, `Error`, `Throwable`, `java.lang.Error` and
      `java.lang.RuntimeException`.

## License

This software is licensed under the terms in the file named "[LICENSE](LICENSE)"
in the root directory of this project.

## Author Information

John Freeman

GantSign Ltd.
Company No. 06109112 (registered in England)
