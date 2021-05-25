C++ and C#
===============

This is a programming style that I use across most of my personal projects and projects that I launched. It's highly inspired by style used by Visual Studio in years 2000 - 2010, with my own improvements.

This style prefers function over form. It may appear ugly to some, but I guarantee, that once you get used to it, navigating through the code will be extremely simple as the code is very clear and concise.

The idea is to make readability as simple as possible, so that when you look at certain line or block of code, it's already absolutely clear to you which scopes each variables have and what purpose they serve, just from their name and you don't need to navigate through the code to find that out.

## Variable and function names (by scope)
* class public: UpperFirst (VariableName)
* class private and protected: lowerFirst (variableName)
* function scope: no_casing_underscores_used_to_separate (variable_name)
* global scope (#defined): UPPERCASE_ONLY (VARIABLE_NAME)
* serializable type: _prefixedWithUnderscore
* function local, unique: suffixed_with_

## Curly bracket alignment

Brackets are always vertically aligned, so that it's absolutely clear where bracket block starts and where it ends, just by looking at it. 

```
namespace MyProgram
{
     class Foo
     {
          public:
              Foo();
              
              void PublicFunction(int some_parameter)
              {
                  // Never ident with tabs just 4 spaces
                  return;
              }
              
          private:
              int foo()
              {
                  return 2 * GLOBAL_CONST;
              }
     }
}
```

In code that doesn't require block of curly brackets (such as if with only one code line) they can be ommited to save space.

```
if (something)
    DoSomething();
```

## Usage of this

It's used everywhere if possible, to make it clear that variables or functions that you work with are in scope of current class instance and also because when you type this-> and autocompletion mechanism is typically trigerred and allow you to easily pick whatever you want to use, which is very practical.

```
void Class::SetN(int some_n)
{
    this->n = some_n;
}
```
