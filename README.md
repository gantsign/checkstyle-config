# GantSign Checkstyle Configuration

[![Build Status](https://travis-ci.org/gantsign/checkstyle-config.svg?branch=master)](https://travis-ci.org/gantsign/checkstyle-config)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Checkstyle configuration for Java code written by GantSign.

# Severity Level

The default severity level is `error`; the goal is to ensure quality rather than
suggest it.

# @SuppressWarnings Support

Because the rules are quite script `@SuppressWarnings` can be used to suppress
errors where necessary. It is the responsibility of the code reviewer to judge
whether suppression of the rule is the appropriate solution.

# Checkstyle Rules

## Style

* [LineLength](http://checkstyle.sourceforge.net/config_sizes.html#LineLength)

    * Line length: maximum 100 chars.
    * Exclusions: package declaration, import declarations and lines containing
      HTTP URLs.

* [Indentation](http://checkstyle.sourceforge.net/config_misc.html#Indentation)

    * Indent: 2 spaces.

* [ArrayTypeStyle](http://checkstyle.sourceforge.net/config_misc.html#ArrayTypeStyle)

    * Array `[]` placement: with type rather than name e.g. `String[]` name.

* [WhitespaceAround](http://checkstyle.sourceforge.net/config_whitespace.html#WhitespaceAround)

    * Whitespace: require whitespace around standard symbols.
    * Exclusions: allow empty constructors/methods/types/lambdas.

* [GenericWhitespace](http://checkstyle.sourceforge.net/config_whitespace.html#GenericWhitespace)

    * Generics: enforce standard whitespace conventions for declaring generic
      type restrictions.

* [MethodParamPad](http://checkstyle.sourceforge.net/config_whitespace.html#MethodParamPad)

    * Method/Constructor declarations & calls: ban padding immediately inside
      parentheses.

* [OperatorWrap](http://checkstyle.sourceforge.net/config_whitespace.html#OperatorWrap)

    * Operator wrapping: when wrapping, operators must be wrapped on to the
      start of the new line rather than remaining on the end of the previous
      line.

* [SeparatorWrap](http://checkstyle.sourceforge.net/config_whitespace.html#SeparatorWrap)

    * Separator wrapping:

        * Commas

            * When wrapping, commas must remain on the end of the line rather
              than being wrapped onto the next line.

        * Dots

            * When wrapping, dots (i.e. in dot notation for accessing object
              members) must be wrapped on to the start of the new line rather
              than remaining on the end of the previous line.

* [NeedBraces](http://checkstyle.sourceforge.net/config_blocks.html#NeedBraces)

    * Braces: braces are required for `if`, `else`, `else if`, `for`, `do` &
      `while`.

* [LeftCurly](http://checkstyle.sourceforge.net/config_blocks.html#LeftCurly)

    * Left braces: must be at the end of the line.

* [RightCurly](http://checkstyle.sourceforge.net/config_blocks.html#RightCurly)

    * Right braces: must be on the same line as `else`, `catch` and `finally`.

* [EmptyBlock](http://checkstyle.sourceforge.net/config_blocks.html#EmptyBlock)

    * Empty blocks: ban empty blocks.

* [EmptyLineSeparator](http://checkstyle.sourceforge.net/config_whitespace.html#EmptyLineSeparator)

    * Empty lines: enforce empty lines after header, package, all import
      declarations, fields, constructors, methods, nested classes, static
      initializers and instance initializers.

* [OneStatementPerLine](http://checkstyle.sourceforge.net/config_coding.html#OneStatementPerLine)

    * Statements: enforce that statements are split onto separate lines.

* [MultipleVariableDeclarations](http://checkstyle.sourceforge.net/config_coding.html#MultipleVariableDeclarations)

    * Multiple variable declarations: ban multiple variable declarations in the
      same statement.

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

* [OverloadMethodsDeclarationOrder](http://checkstyle.sourceforge.net/config_coding.html#OverloadMethodsDeclarationOrder)

    * Declaration order: require overloaded methods be grouped together.

* [RedundantModifier](http://checkstyle.sourceforge.net/config_modifier.html#RedundantModifier)

    * Modifiers: ban redundant modifiers (e.g. public for methods in an
      interface).

* [ModifierOrder](http://checkstyle.sourceforge.net/config_modifier.html#ModifierOrder)

    * Modifier order: ensure modifiers appear in the following order:

        1. `public`
        2. `protected`
        3. `private`
        4. `abstract`
        5. `static`
        6. `final`
        7. `transient`
        8. `volatile`
        9. `synchronized`
        10. `native`
        11. `strictfp`

* [AnnotationLocation](http://checkstyle.sourceforge.net/config_annotation.html#AnnotationLocation)

    * Annotation location

        * Variable declarations

            * Multiple annotations are allowed on the same line for variable
              declarations.

        * All other annotated elements

            * Annotations must be between JavaDoc and declaration, must be on
              separate lines.

* [AtclauseOrder](http://checkstyle.sourceforge.net/config_javadoc.html#AtclauseOrder)

    * Doclet tag order: doclet tags must appear in the following order:

         1. `@author`
         2. `@version`
         3. `@param`
         4. `@return`
         5. `@throws`
         6. `@exception`
         7. `@see`
         8. `@since`
         9. `@serial`
         10. `@serialField`
         11. `@serialData`
         12. `@deprecated`

* [JavadocTagContinuationIndentation](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocTagContinuationIndentation)

    * JavaDoc: continuation indent must be 4 spaces.

* [SingleLineJavadoc](http://checkstyle.sourceforge.net/config_javadoc.html#SingleLineJavadoc)

    * JavaDoc: ensure that JavaDoc fits on within the line length and doclet
      tags are at the beginning of a line.

* [AvoidStarImport](http://checkstyle.sourceforge.net/config_imports.html#AvoidStarImport)

    * Imports: ban `*` imports.

* [RedundantImport](http://checkstyle.sourceforge.net/config_imports.html#RedundantImport)

    * Imports: ban redundant imports.

* [CustomImportOrder](http://checkstyle.sourceforge.net/config_imports.html#CustomImportOrder)

    * Import order:

        1. Static imports
        2. Blank line (only if both static and ordinary import are specified)
        3. Ordinary imports

        All imports are ordered alphabetically.

## Naming Conventions

* [AbbreviationAsWordInName](http://checkstyle.sourceforge.net/config_naming.html#AbbreviationAsWordInName)

    * Naming: force abbreviations to be treated as words e.g. `XmlHttpRequest`
      or `XML_HTTP_REQUEST` rather than `XMLHTTPRequest`.

* [PackageName](http://checkstyle.sourceforge.net/config_naming.html#PackageName)

    * Package name: ASCII letters and digits only, all lowercase, root package
      must be letters only, first char of each package must be a letter.

* [TypeName](http://checkstyle.sourceforge.net/config_naming.html#TypeName)

    * Class/interface/enum name: ASCII letters and digits only, first char must
      be an uppercase letter, second char must be a lower case letter or a
      digit, min length 3 alphanumeric chars.

* [MethodName](http://checkstyle.sourceforge.net/config_naming.html#MethodName)

    * Method name: ASCII letters and digits only, first char must be a lowercase
      letter, second char must be a lower case letter or a digit, min length 3
      alphanumeric chars.

* [ParameterName](http://checkstyle.sourceforge.net/config_naming.html#ParameterName)

    * Parameter name: ASCII letters and digits only, first char must be a
      lowercase letter, second char must be a lower case letter or a digit, min
      length 3 alphanumeric chars.

* [CatchParameterName](http://checkstyle.sourceforge.net/config_naming.html#CatchParameterName)

    * Catch variable name: must be either:

        * The single character `e`.
        * ASCII letters and digits only, first char must be a lowercase letter,
          second char must be a lower case letter or a digit, min length 3
          alphanumeric chars.

* [LocalVariableName](http://checkstyle.sourceforge.net/config_naming.html#LocalVariableName)

    * Local variable name: must be either:

        * ASCII letters and digits only, first char must be a lowercase letter,
          second char must be a lower case letter or a digit, min length 3
          alphanumeric chars.
        * A single character: only permitted for the index in a for loop.

* [ClassTypeParameterName](http://checkstyle.sourceforge.net/config_naming.html#ClassTypeParameterName)

    * Generic type name (class): must be either:

        * One ASCII letter optionally followed by a digit.
        * ASCII letters and digits only, first char must be an uppercase letter,
          must end with an uppercase `T`, min length 2 alphanumeric chars.

* [MethodTypeParameterName](http://checkstyle.sourceforge.net/config_naming.html#MethodTypeParameterName)

    * Generic type name (method): must be either:

        * One ASCII letter optionally followed by a digit.
        * ASCII letters and digits only, first char must be an uppercase letter,
          must end with an uppercase `T`, min length 2 alphanumeric chars.

* [InterfaceTypeParameterName](http://checkstyle.sourceforge.net/config_naming.html#InterfaceTypeParameterName)

    * Generic type name (interface): must be either:

        * One ASCII letter optionally followed by a digit.
        * ASCII letters and digits only, first char must be an uppercase letter,
          must end with an uppercase `T`, min length 2 alphanumeric chars.

## Quality Checks

* [OuterTypeFilename](http://checkstyle.sourceforge.net/config_misc.html#OuterTypeFilename)

    * Type name: ensure the outer class/interface/enum matches the file name.

* [IllegalTokenText](http://checkstyle.sourceforge.net/config_coding.html#IllegalTokenText)

    * Escape sequences: use special escape sequence rather than the
      octal/Unicode escape sequences for: `\b`, `\t`, `\n`, `\f`, `\r`, `\"`,
      `\'` and `\\`.

* [AvoidEscapedUnicodeCharacters](http://checkstyle.sourceforge.net/config_misc.html#AvoidEscapedUnicodeCharacters)

    * Unicode escapes: force use of UTF-8 characters rather than Unicode escape
      sequences.

* [MissingSwitchDefault](http://checkstyle.sourceforge.net/config_coding.html#MissingSwitchDefault)

    * Switch: all switch statements must have a default.

* [FallThrough](http://checkstyle.sourceforge.net/config_coding.html#FallThrough)

    * Switch: fall though cases must have a `"fall through"` comment.

* [UpperEll](http://checkstyle.sourceforge.net/config_misc.html#UpperEll)

    * Longs: long literals must have an uppercase `L` suffix.

* [NoFinalizer](http://checkstyle.sourceforge.net/config_coding.html#NoFinalizer)

    * Finalize methods: `finalize()` methods are banned.

* [VariableDeclarationUsageDistance](http://checkstyle.sourceforge.net/config_coding.html#VariableDeclarationUsageDistance)

    * Declaration usage: ensure the distance between declaration of a variable
      and its use is no more than 3.

* [JavadocType](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocType)

    * JavaDoc: Ensure classes, interfaces and enums have class level JavaDoc.

* [NonEmptyAtclauseDescription](http://checkstyle.sourceforge.net/config_javadoc.html#NonEmptyAtclauseDescription)

    * JavaDoc: Ensure `@param`/`@return`/`@throws`/`@deprecated` description
      isn't empty.

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

* [ParameterNumber](http://checkstyle.sourceforge.net/config_sizes.html#ParameterNumber)

    * Methods/constructors: limit the number of parameters that can be declared
      in a method/constructor to 3.

* [ExplicitInitialization](http://checkstyle.sourceforge.net/config_coding.html#ExplicitInitialization)

    * Initialization: ban explicitly initializing fields to their default
      values.

* [IllegalInstantiation](http://checkstyle.sourceforge.net/config_coding.html#IllegalInstantiation)

    * Wrapper types: ban using constructor of wrapper types.

* [IllegalType](http://checkstyle.sourceforge.net/config_coding.html#IllegalType)

    * Collections: enforce using Collection interfaces for return types,
      parameter types, fields, and local variables for basic collection
      implementation types.

* [MutableException](http://checkstyle.sourceforge.net/config_design.html#MutableException)

    * Exceptions: ban mutable exceptions; be aware this only checks the fields
      in the exception are declared final.

* [EmptyCatchBlock](http://checkstyle.sourceforge.net/config_blocks.html#EmptyCatchBlock)

    * Exception handling: ban empty catch blocks.

* [IllegalCatch](http://checkstyle.sourceforge.net/config_coding.html#IllegalCatch)

    * Exception handling: ban catching `java.lang.Exception`,
      `java.lang.Throwable` and `java.lang.RuntimeException`.

* [IllegalThrows](http://checkstyle.sourceforge.net/config_coding.html#IllegalThrows)

    * Exception handling: ban throwing `java.lang.Throwable`, `java.lang.Error`
    and `java.lang.RuntimeException`.

* [ThrowsCount](http://checkstyle.sourceforge.net/config_design.html#ThrowsCount)
    * Throws clause: limit the number of exceptions that can be declared in the
      throws clause to 2.

## License

This software is licensed under the terms in the file named "[LICENSE](LICENSE)"
in the root directory of this project.

## Author Information

John Freeman

GantSign Ltd.
Company No. 06109112 (registered in England)
