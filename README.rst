.. default-role:: code


###################################
 Desktop notifications from Neovim
###################################

This plugin provides implementations of the `vim.notify` function which use the
operating system's notification facility to display native notifications.
Currently only shelling out to `notify-send` is implemented, but other
implementations can be added. Contributions are very welcome.


Installation and dependencies
#############################

First install this plugin like any other Neovim plugins. You will also need to
satisfy dependencies for the particular implementation you wish to use.

Shelling out to `notify-send`:
   Requires `notify-send` to be in your `$PATH`


Usage
#####

You can try calling the implementation directly. Example:

.. code:: vim
   lua require('desktop_notify').notify_send('Hello from Neovim')

Once you execute the above command in your running Neovim instance a
notification native to your OS should open up. In practice you will probably
want to overwrite the default implementation with this one.

.. code:: lua
   vim.notify = require('desktop_notify').notify_send


License
#######

Released under the MIT (Expat) license. Please refer to the `LICENSE`_ file for
details.

.. _LICENSE: LICENSE.txt
