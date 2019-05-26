# roachlite
Indented to be a sane replacement to PortRoach

PortRoach is based on the sqlports database, and was written as a variation on portscout.

Unfortunately, PortRoach is really slow and clunky, and insists on using Postgres for reasonable performance.

We can definitely do better and smaller
- limit to sqlite, that way we just keep our adjunct table on the side, and reuse sqlports directly. Synchronization should be automatic.
- don't reroll our own template engine. Template Toolkit is just fine.
- use ftp(1) directly, because it's what the other tools do. Added bonus: we're automatically uptodate wrt https certificates AND IPv6, which is hard to do in perl proper.
