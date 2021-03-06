# Issue
> Issue:指需要一起讨论解决的问题（所以github使用的时issue）

> problem:客观存在的难以解决的问题

> question:口头提问

# Fork

有这样一种情形。

有一个叫做Joe的程序猿写了一个游戏程序，而你可能要去改进它。并且Joe将他的代码放在了GitHub仓库上。

1. Fork他的仓库：这是GitHub操作，这个操作会复制Joe的仓库（包括文件，提交历史，issues，和其余一些东西）。复制后的仓库在你自己的GitHub帐号下。目前，你本地计算机对这个仓库没有任何操作。

2. Clone你的仓库：这是Git操作。使用该操作让你发送"请给我发一份我仓库的复制文件"的命令给GitHub。现在这个仓库就会存储在你本地计算机上。

3. 更新某些文件：现在，你可以在任何程序或者环境下更新仓库里的文件。

4. 提交你的更改：这是Git操作。使用该操作让你发送"记录我的更改"的命令至GitHub。此操作只在你的本地计算机上完成。

5. 将你的更改push到你的GitHub仓库：这是Git操作。使用该操作让你发送"这是我的修改"的信息给GitHub。Push操作不会自动完成，所以直到你做了push操作，GitHub才知道你的提交。

6. 给Joe发送一个pull request：如果你认为Joe会接受你的修改，你就可以给他发送一个pull request。这是GitHub操作，使用此操作可以帮助你和Joe交流你的修改，并且询问Joe是否愿意接受你的"pull request"，当然，接不接受完全取决于他自己。

7. 如果Joe接受了你的pull request，他将把那些修改拉到自己的仓库！
