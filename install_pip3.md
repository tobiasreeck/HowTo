## "TypeError: 'module' object is not callable"
#### How to install Pip3 for Python3

Downloadind pip3 in itself is not difficult. With my ubuntu version, i simply entered this in the console to install pip3:

`sudo apt install python3-pip`

It seemed to work, but then i entered `pip3 install --upgrade pip` to update pip3 to the latest version.
After that, i tried to install a module with pip3, but all i got, was this error message:

````Traceback (most recent call last):
  File "/usr/bin/pip3", line 11, in <module>
    sys.exit(main())
TypeError: 'module' object is not callable
Error in sys.excepthook:
Traceback (most recent call last):
  File "/usr/lib/python3/dist-packages/apport_python_hook.py", line 109, in apport_excepthook
    pr.add_proc_info(extraenv=['PYTHONPATH', 'PYTHONHOME'])
  File "/usr/lib/python3/dist-packages/apport/report.py", line 550, in add_proc_info
    self.add_proc_environ(pid, extraenv)
  File "/usr/lib/python3/dist-packages/apport/report.py", line 619, in add_proc_environ
    env = _read_file('environ', dir_fd=proc_pid_fd).replace('\n', '\\n')
  File "/usr/lib/python3/dist-packages/apport/report.py", line 73, in _read_file
    with open(path, 'rb', opener=lambda path, mode: os.open(path, mode, dir_fd=dir_fd)) as fd:
  File "/usr/lib/python3/dist-packages/apport/report.py", line 73, in <lambda>
    with open(path, 'rb', opener=lambda path, mode: os.open(path, mode, dir_fd=dir_fd)) as fd:
TypeError: argument should be integer or None, not list

Original exception was:
Traceback (most recent call last):
  File "/usr/bin/pip3", line 11, in <module>
    sys.exit(main())
TypeError: 'module' object is not callable
````
I uninstalled pip3 because i was scared that i might destroy my python3 with pip3. I read a bit about pip3 and several forums mentioned, that one shouldn't install modules with pip3 on your system directly, but should instead use so called "virtual environments". These are basically supposed to be copies of the original system, but if anything should happen to them, your system is still fine.

I successfully uninstalled pip3 with:

`sudo apt-get --purge autoremove pyhton3-pip`

After reading a bit in forums, i couldn't really figure out what i did wrong. So i began with installing pip3 again, with the same command at the top of this aritcle.

This time, i proceeded to upgrade pip3 with the following command:

`python3 -m pip install --upgrade pip`

And again, pip3 was usable (i coulnd't even call "pip3 --version").

I fixed that, by simply entering:

`python3 -m pip uninstall pip`

Which appearantly uninstalls some other pip3 (or simply "pip", which is the pip-version before python3), so now entering "pip3" works just fine.

Fin

[Source](https://stackoverflow.com/questions/58386953/i-have-a-issue-with-pip3)
