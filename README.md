# GitTest
Testing how git stores weird file types

1. Windows Junction Points NO--see below
2. Windows Symlinks NO--see below

C:\Repos\GitTest>mkdir TargetLocation

C:\Repos\GitTest>mklink /J Junction TargetLocation
Junction created for Junction <<===>> TargetLocation

C:\Repos\GitTest>mklink Junction TargetLocation
Access is denied.

C:\Repos\GitTest>mklink Symlink TargetLocation
symbolic link created for Symlink <<===>> TargetLocation

C:\Repos\GitTest>dir
 Volume in drive C is UNC-R9P59K8
 Volume Serial Number is 4667-14A2

 Directory of C:\Repos\GitTest

01/25/2016  02:41 PM    <DIR>          .
01/25/2016  02:41 PM    <DIR>          ..
01/25/2016  02:41 PM    <JUNCTION>     Junction [C:\Repos\GitTest\TargetLocation]
01/25/2016  02:40 PM               103 README.md
01/25/2016  02:41 PM    <SYMLINK>      Symlink [TargetLocation]
01/25/2016  02:41 PM    <DIR>          TargetLocation
               2 File(s)            103 bytes
               4 Dir(s)  50,656,153,600 bytes free

C:\Repos\GitTest>git status
On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Symlink

nothing added to commit but untracked files present (use "git add" to track)

C:\Repos\GitTest>git add *
error: readlink("Symlink"): Function not implemented
error: unable to index file Symlink
fatal: adding files failed
