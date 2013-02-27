# DjangoNoseTestRunner

Do you hate waiting seconds for the complete test suite to finish when all
you're trying to do is get this one test to pass? So do we.

DjangoNoseTestRunner is a plugin for Sublime Text 2 that allows you to run
the test under cursor in the currently opened test file.

## Example usage

Open one of your test files, navigate to a test function you want to run,
and hit Ctrl-T. Look at the output console for the test results.

## Installation

* Download the plugin from GitHub - here's a link to the
  [current master](https://github.com/dobarkod/DjangoNoseTestRunner/archive/master.zip).
* Unzip the plugin to your Sublime Text Packages directory
  (eg. `~/.config/sublime-text-2/Packages/` on Linux)

## Configuration

If you're using Virtualenv or have separate Django settings module for tests,
you'll want to add a per-project configuration so that the plugin can
run your tests properly.

To add the per-project configuration, open your project file (Project->Edit
in the menu), and add the following under the `settings` key:

        "django-nose-test": {
            "python": "/path/to/your/virtualenv/bin/python",
            "django-settings": "myproject.settings.test"
        }

If there's no `settings` key in the project file, just add one and add the
above under it.

## Usage

Plugin can run a single test, multiple tests, entire test case or the entire
file.

To run a single test, just position your cursor somewhere in the test function
body and hit Ctrl-T.

To run multiple tests, select (any) bit of text from each of the functions
you want to run and hit Ctrl-T. The functions can be in the same test
case class, or in the separate classes.

You can also run the entire test case (all the test functions in the class),
or multiple test cases, by selecting (any) bit of text from the class body
that's *not* in the the test function (eg. `class FooTest(TestCase):` lines).

If the cursor is not inside any test function or test case class when you hit
Ctrl-T, all the test from the file (but just that file) will be run.

## License and copyright

Copyright &copy; 2013. DjangoNoseTestRunner contributors

You can use, modify and distribute this plugin under the terms of the
[MIT public license](http://opensource.org/licenses/MIT).
