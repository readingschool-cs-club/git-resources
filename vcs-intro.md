Introduction to VCSs & where Git comes in
=========================================

Some history
------------

Git is a [version control system](!Wikipedia "Revision control") (VCS)
which was originally developed by [Linus Torvalds](!Wikipedia) to use
for developing the Linux kernel.


What's the point of a VCS?
--------------------------

Suppose you're starting development on a big project. You decide that
you to backup your code periodically in case you need to retrieve old
code (for example if you changed something which introduced a bug, or if
you accidentally deleted a section of code).

You could just set up a script to backup your project directory every
day to another directory, or maybe an external drive. But then if you do
lots of work in a day and then lose your data, you'd have no way to
retrieve it. So you need to **choose when to backup**.

From now on, I'll call backups 'snapshots'. Now we have a system where
every time you want to create a snapshot, you make a copy of your entire
project directory into a new directory, say `snapshot-X` where X is the
snapshot number.

So that you can easily remember what you did in each snapshot, you add a
`message` file which contains a short summary of the changes you made.

And now we've come to the basics of a VCS. A new snapshot is created
with each commit, and a message (along with a date and author) is
attached to each commit.


What IS a VCS?!
---------------

A VCS is basically a program which keeps 'snapshots' of your code every
time you tell it you've changed something. A useful VCS allows you to
look at any snapshot you want. They also make sure not to waste space
when snapshotting, e.g. if a file wasn't edited in a snapshot then it
isn't copied, since it exists in a previous snapshot. These are just a
few of the advantages of using a VCS like Git instead of just making
copies of your code every now and then.

*NOTE: Git is NOT a backup program! Backups should be made to external &
offsite drives. Git might fulfill part of the functionality of a backup
application, but it's not meant for it, so don't use Git for backup
purposes!*


Further information
-------------------

If you're interested in Git and want to understand it more deeply, you
might like to check out Tom Preston-Werner's ['The Git
Parable'](http://tom.preston-werner.com/2009/05/19/the-git-parable.html).
My VCS explanation was taken from the first part of his fantastic
parable.
