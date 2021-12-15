NoSeeVar 1.21

http://www.100acrebloodbath.com/files/lib/nsv12_plugin.zip


[HISTORY]

1.21
- Movement cvar bug fix

1.2
- Additions can be made to nsv.cfg without the need for a server 
restart (map change only to have changes take effect).
- Values can now be assigned to new or modified cvars directly
through nsv.cfg
- Bug fix that forced flag assigned to FCVAR_EXTDLL all the time,
regardless of flag modifiers.
- NSV's position in the Metamod plugin.ini no longer matters.

1.1
- Revised installation process to use standard <mod>/addons directory
structure. Those with 1.0 installations should move their cfg files to
<mod>/addons/nsv as described below.
- Revised the build optimizations.

1.0
- Initial release


[OVERVIEW]

NoSeeVar (NSV) allows admins to remove Half-Life cvars (both from the
server and other plugins) from the the public server query list. There
are several reasons why an admin might want to do this.

1) RuleInfo errors are being generated on the server due to too many
cvars consuming too much memory.
2) GameSpy or other server browsers choking on excessive public cvars
from the server.
3) Anyone wishing to hide the fact that a particular mod is running
(for security and other reasons)
4) Housekeeping. Many cvars made public by plugins simply don't need
to be public. They increase the size of the server cvar list, increase
bandwidth usage by server monitors and contribute to query 'bloat'.

NSV works by registering the CVAR if it does not yet exist, or
re-casting the flags if it does. (Incidentially, NSV can be used to
create your own custom-use cvars).


[USAGE]

1) Create an addons/nsv directory in your mod folder (example: cstrike/addons/nsv)
2) Place nsv_mm.dll/so and nsv.cfg in the addons/nsv folder you created. (failure
to place the cfg in this directory will prevent NSV from working properly).
3) Add/modify cvar values to your nsv.cfg as desired.
4) Add an appropriate reference to the nsv_mm.dll/so plugin in your
Metamod plugins.ini file.
5) Restart your server.

NSV has two cvars of its own:

nsv_list: This holds a reference to all cvars blocked by NSV. This
is provided as a convenience to game browser engines. Those looking
for particular cvars can search 'nsv_list' as well to see if it exists
but is being blocked.

nsv_build_list: If set to 1, this will allow the nsv_list to be
built. Add 'nsv_build_list 1' to your server.cfg to enable nsv_list.

Note that nsv_list is itself a public cvar ONLY if nsv_build_list = 1.


[CAUTION]

Making some cvars invisible to public queries could have adverse
effects (for example, phpua_mm_port, sparky_version or any other cvar
that works as part of a system and needs to be 'seen' by other
components). NSV will not allow you to block core Half-Life cvars.
However, ultimately it is up to the admin to exercise care and caution
when choosing what cvars to block.


[SUPPORT]

http://www.100acrebloodbath.com/forums  (HL Server -> Buzz's Plugins)


Thanks to Brain, Punisher, Grumpy Gourmet and everyone who has provided
feedback.


