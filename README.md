jorsn-musl
===========

My own [musl] overlay for [gentoo] in addition to the [official one][musl-overlay].

Here I place ebuilds that I use but that aren't accepted by gentoo
package maintainers. Use at Your own risk – i cannot test ebuilds against all use
flag combinations or architectures.

**DEPRECATION WARNING (2019-05-04): *As I have switched from Gentoo to NixOS, this is no longer maintained, and won't probably be in the near future.***


Installation
-------------

You can either install the overlay via the [repos.conf method][repos.conf] or
use [layman].


### repos.conf

Put a file like this in `/etc/portage/repos.conf/jorsn-musl.conf`:

	[jorsn-musl]
	location = <some-path>/jorsn-musl
	sync-type = git
	sync-uri = https://github.com/jorsn/jorsn-gentoo-musl.git
	auto-sync = yes

Then, sync your portage tree:

	$ emaint sync -r jorsn-musl


### layman

Then, add the overlay to layman and sync:

	$ layman -o https://raw.githubusercontent.com/jorsn/jorsn-gentoo-musl/master/jorsn-musl.xml -f -a jorsn-musl
	$ emaint sync -r jorsn-musl



[musl]:         https://www.musl-libc.org
[gentoo]:       https://gentoo.org
[musl-overlay]: https://github.com/gentoo/musl
[repos.conf]:   https://wiki.gentoo.org/wiki/Repos.conf
[layman]:       https://wiki.gentoo.org/wiki/Layman


<!-- vim: sw=4 ts=4
-->
