# DjangoNoseTestRunner

Do you hate waiting seconds for the complete test suite to finish when all
you're trying to do is get this one test to pass? So do we.

DjangoNoseTestRunner is a plugin for Sublime Text 2 that allows you to run
the test under cursor in the currently opened test file.

The plugin supports running tests using `django-nose` (recommended) or
the standard Django test runner.

## Example usage

Open one of your test files, navigate to a test function you want to run,
and hit Ctrl-T. Look at the output console for the test results.

## Installation

* Download the plugin from GitHub - here's a link to the
  [current master](https://github.com/dobarkod/DjangoNoseTestRunner/archive/master.zip).
* Unzip the plugin to your Sublime Text Packages directory
  (eg. `~/.config/sublime-text-2/Packages/` on Linux)

## Configuration

If you're using Virtualenv, have separate Django settings module for tests or
want to use nose, you'll want to add a per-project configuration so that the
plugin can run your tests properly.

To add the per-project configuration, open your project file (Project->Edit
in the menu), and change it to looks like this:

    {
        "folders": [ ... ],
        "settings":
        {
            "django-nose-test": {
                "python": "/path/to/your/virtualenv/bin/python",
                "django-settings": "myproject.settings.test",
                "doted-notation": true,  // optional and only used if "use-nose" is false
                "apps-dir": "my_apps",  // optional and only used if "doted-notation" is true
                "use-nose": true,
                "nose-options": ["--nocapture"] // optional and only used if use-nose is true
            }
        }
    }

The `django-nose-test` dictionary are the settings for DjangoNoseTestRunner.

The `doted-notation` required for Django 1.6 or [django-discover-runner](https://github.com/jezdez/django-discover-runner).

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

If you're using nose, the tests are located per-file (as described above). If
you're using the standard Django test runner, the tests are per-app (one
test method, one TestCase or the entire app test suite).

## License and copyright

Copyright &copy; 2013. DjangoNoseTestRunner contributors

You can use, modify and distribute this plugin under the terms of the
[MIT public license](http://opensource.org/licenses/MIT).
