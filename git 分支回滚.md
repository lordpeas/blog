﻿`f_nuohe_v2.0` 上提交了一些新功能，之后可能不发布生产，所以需要把新功能迁移到一个新分支上，`f_nuohe_v2.0` 回退到新功能第一次提交的地方。
1. 在 `f_nuohe_v2.0` 的最后一次提交，切一个新分支出来 `f_nuohe_v2.0_portrayal`，推送到远端
2. 在 `f_nuohe_v2.0` 新功能第一次提交的地方，右键，重置到这次提交，会有三种合并代码的方式：
```
git reset --mixed：此为默认方式，不带任何参数的git reset，即时这种方式，它回退到某个版本，只保留源码，回退commit和index信息
git reset --soft：回退到某个版本，只回退了commit的信息，不会恢复到index file一级（修改的源码会保留）。如果还要提交，直接commit即可
git reset --hard：彻底回退到某个版本，本地的源码也会变为上一个版本的内容，此命令 慎用！
```
soft 回退 commit：本地提交重置到选择的那一次
mixed 回退 commit，index：索引重置，后面提交的文件存到暂存区，从远端重新拉取后面的提交（推荐，可以查看文件修改，选择文件丢弃）
hard 回退 commit，index，文件变化：后面提交修改的文件完全丢弃

