=====================
CHANGELOG conventions
=====================

These conventions are highly advisable but not mandatory. They can be slightly
modify on different projects. This convention is only meant to help you getting
started.


What’s a change log?
====================

A change log is a file which contains a curated, chronologically ordered
list of notable changes for each version of an open source project.


What’s the point of a change log?
=================================

To make it easier for users and contributors to see precisely what
notable changes have been made between each release (or version) of the
project.


Why should I care?
==================

Because software tools are for people.

There's a `talk with Adam Stacoviak and Jerod Santo on The
Changelog <http://5by5.tv/changelog/127>`__ (fitting, right?) podcast
about why open source maintainers and contributors should care, and the
motivations behind this project.


What makes a good change log?
=============================

A good change log sticks to these principles:

* It’s made for humans, not machines, so legibility is crucial.
* Easy to link to any section (hence ReStructuredText over plain text).
* One sub-section per version.
* List releases in reverse-chronological order (newest on top).
* Write all dates in ``YYYY-MM-DD`` format. (Example: ``2012-06-02``
  for ``June 2nd, 2012``.) It’s international,
  `sensible <http://xkcd.com/1179/>`__, and language-independent.
* Explicitly mention whether the project follows `Semantic
  Versioning <http://semver.org>`__.
* Each version should:

  - List its release date in the above format.
  - Group changes to describe their impact on the project, as follows:

    + ``Added`` for new features.
    + ``Changed`` for changes in existing functionality.
    + ``Deprecated`` for once-stable features removed in upcoming releases.
    + ``Removed`` for deprecated features removed in this release.
    + ``Fixed`` for any bug fixes.
    + ``Security`` to invite users to upgrade in case of vulnerabilities.


How can I minimize the effort required?
=======================================

Always have an ``"Unreleased"`` section at the top for keeping track of
any changes.

This serves two purposes:

* People can see what changes they might expect in upcoming releases
* At release time, you just have to change ``"Unreleased"`` to the
   version number and add a new ``"Unreleased"`` header at the top.


What makes unicorns cry?
========================

Alright… let’s get into it.

* **Dumping a diff of commit logs.** Just don’t do that, you’re helping
  nobody.
* **Not emphasizing deprecations.** When people upgrade from one
  version to another, it should be painfully clear when something will
  break.
* **Dates in region-specific formats.** In the U.S., people put the
  month first ("06-02-2012" for June 2nd, 2012, which makes *no*
  sense), while many people in the rest of the world write a
  robotic-looking "2 June 2012", yet pronounce it differently.
  "2012-06-02" works logically from largest to smallest, doesn't
  overlap in ambiguous ways with other date formats, and is an `ISO
  standard <http://www.iso.org/iso/home/standards/iso8601.htm>`__.
  Thus, it is the recommended date format for change logs.

There’s more. Help collect those unicorn tears by `opening an
issue <https://github.com/olivierlacan/keep-a-changelog/issues>`__ or a
pull request.


Is there a standard change log format?
======================================

Sadly, no.


What should the change log file be named?
=========================================

``CHANGELOG.rst`` is the best convention so far.

Some projects also use ``HISTORY.txt``, ``HISTORY.md``, ``History.md``,
``NEWS.txt``, ``NEWS.md``, ``News.txt``, ``RELEASES.txt``,
``RELEASE.md``, ``releases.md``, etc.

It’s a mess. All these names only makes it harder for people to find it.


Why can’t people just use a ``git log`` diff?
=============================================

Because log diffs are full of noise — by nature. They could not make a
suitable change log even in a hypothetical project run by perfect humans
who never make typos, never forget to commit new files, never miss any
part of a refactoring. The purpose of a commit is to document one atomic
step in the process by which the code evolves from one state to another.
The purpose of a change log is to document the noteworthy differences
between these states.

As is the difference between good comments and the code itself, so is
the difference between a change log and the commit log: one describes
the *why*, the other the how.


Example
=======


::

	==========
	Change Log
	==========

	All notable changes to this project will be documented in this file.
	This project adheres to [Semantic Versioning](http://semver.org/).

	[Unreleased][unreleased]
	========================

	Changed
	-------

	* Improve argument against commit logs.

	[0.0.8] - 2015-02-17
	====================

	Changed
	-------

	* Update year to match in every README example.
	* Reluctantly stop making fun of Brits only, since most of the world
	  writes dates in a strange way.

	Fixed
	-----

	* Fix typos in recent README changes.
	* Update outdated unreleased diff link.

	[0.0.7] - 2015-02-16
	====================

	Added
	-----

	* Link, and make it obvious that date format is ISO 8601.

	Changed
	-------

	* Clarified the section on "Is there a standard change log format?".

	Fixed
	-----

	* Fix Markdown links to tag comparison URL with footnote-style links.

	[0.0.6] - 2014-08-09
	====================

	Added
	-----

	* Better explanation of the difference between the file ("CHANGELOG")
	  and its function "the change log".

	Changed
	-------

	* Refer to a "change log" instead of a "CHANGELOG" throughout the site
	  to differentiate between the file and the purpose of the file — the
	  logging of changes.

	Removed
	-------

	* Remove empty sections from CHANGELOG, they occupy too much space and
	  create too much noise in the file. People will have to assume that the
	  missing sections were intentionally left out because they contained no
	  notable changes.

