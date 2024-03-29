# Archive-Tar-Stream
Archive::Tar::Stream - pure perl IO-friendly tar file management

# DESCRIPTION

This module was previously known as ME::TarStream and created
as part of the backup system at FastMail.FM a few years ago.
The first commit was Tue Feb 20 03:21:43 2007 +0000

# NEW IN VERSION 0.03

This is Archive-Tar-Stream 0.02 with a NODIE feature added. Use it thusly:-

	use Archive::Tar::Stream 0.03; $Archive::Tar::Stream::NODIE=1; # prevents calls from doing an unwanted die() on you

# RATIONALE

Why this instead of just using gnu tar, or any of the other
Archive:: packages?  In a word, IO.  Actually that's two
words if you unpack the acronym.

Unpacking a tar file in order to remove some parts and then
re-pack it causes a lot of IO.  Particularly for the unlink
afterwards.  Working in tmpfs is OK, until your files get
big.

We needed to repack incremental backups of up to 100Gb of
emails, one file per email.  Starting with a .tar.gz, and
ending with a .tar.gz.  Hence something that could sit in
a pipe like this:

zcat old.tar.gz | ./decider | gzip > new.tar.gz


# INSTALLATION

To install this module, run the following commands:

	perl Makefile.PL
	make
	make test
	make install

# SUPPORT AND DOCUMENTATION

After installing, you can find documentation for this module with the
perldoc command.

    perldoc Archive::Tar::Stream

You can also look for information at:-

    https://github.com/gitcnd/Archive-Tar-Stream

    RT, CPAN's request tracker (report bugs here)
        http://rt.cpan.org/NoAuth/Bugs.html?Dist=Archive-Tar-Stream

    AnnoCPAN, Annotated CPAN documentation
        http://annocpan.org/dist/Archive-Tar-Stream

    CPAN Ratings
        http://cpanratings.perl.org/d/Archive-Tar-Stream

    Search CPAN
        http://search.cpan.org/dist/Archive-Tar-Stream/

Upstream source code is on GitHub:

        http://github.com/brong/Archive-Tar/Stream/


# LICENSE AND COPYRIGHT

Copyright (C) 2011-2014 Bron Gondwana
Copyright (C) 2019 Chris Drake

This program is free software; you can redistribute it and/or modify it
under the terms of either: the GNU General Public License as published
by the Free Software Foundation; or the Artistic License.

See http://dev.perl.org/licenses/ for more information.

