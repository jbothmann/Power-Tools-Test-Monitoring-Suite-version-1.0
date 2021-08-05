Set up your python environment for creating forks

Newest version of python 3:
	url: https://www.python.org/downloads/

Add tkTheme to your project directory:
	github: https://github.com/jbothmann/tkTheme

Install Flask:
	url: https://flask.palletsprojects.com/en/2.0.x/
	pip command: $ pip install Flask

Install pySerial:
	url: https://pythonhosted.org/pyserial/
	pip command: $ pip install pyserial

Install Requests:
	url: https://docs.python-requests.org/en/master/
	pip command: $ python -m pip install requests

Install pyInstaller:
	url: https://pyinstaller.readthedocs.io/en/stable/index.html
	pip command: $ pip install pyinstaller


pyinstaller freezing commands:
	freeze test manager: $ pyinstaller -w -i="snap.ico" --add-data "themes.json";. --add-data "fonts.json";. --add-data "config.json";. --add-data "Test Manager Tutorial.pdf";. "Test Manager.py"
	freeze test viewer: $ pyinstaller -w -i="snap.ico" --add-data "themes.json";. --add-data "fonts.json";. --add-data "config.json";. --add-data "Test Viewer Tutorial.pdf";. "Test Viewer.py"


Style Idiosyncracies:
	ii is an integer iterator to be used in for loops
	oo is an object iterator to be used in enhanced/pythonic for loops
	for nested for loops, use i1, i2, i3... or o1, o2, o3

	tkTheme is a python package that I created to make painting the program faster and neater.
	contains two objects: Theme, which just configures color, and ThemeAndFont, which configures text as well
	In both applications, the theming object is named T.
	The theme can be applied to a widget either by calling T.apply(widget) or by calling T(widget)

Known Issues:
-The windows-style title and menu bar cannot be configured with different colors or fonts.  This is a limitation of Tkinter, and the only way to fix it would be to rebuild these items with Tkinter components.

-When the Test Manager program ends, this gets logged in the console:
	Exception ignored in: <function Image.__del__ at 0x000001AEB064A040>
	Traceback (most recent call last):
	  File "C:\Users\np0083\AppData\Local\Programs\Python\Python38\lib\tkinter\__init__.py", line 4015, in __del__
	TypeError: catching classes that do not inherit from BaseException is not allowed
It's a bug with Tkinter, due to the Image definition referencing an exception type during teardown, after that exception type has already been deleted.
The issue is harmless, so it's best to just ignore it.
