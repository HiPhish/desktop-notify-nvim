.. default-role:: code

################################
 Hacking on desktop-notify.nvim
################################

There is only one user-facing Lua file, named `desktop_notify`, which contains
every implementation. This way the user-facing interface is small and users can
pick the one implementation they want. More complicated implementations can
use separate Lua files, but the public file must contain the entry point into
the implementation, even if it is just a simple re-export.

For every implementation document it and document its dependencies. Users
should be able to check for dependencies at runtime and pick their
implementation accordingly. Example:

.. code:: lua
   local dn = require 'desktop_notify'

   -- Safely swap out the implementation only if the dependency is available
   if vim.fn.executable('notify-send') ~= 0 then
       vim.notify = dn.notify_send
   end
