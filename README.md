# git-learning
This is repository where I learn git


### Markdown language
* an easy-to-read, easy-to-write format for writing for the web
* some descriptions: [github版](https://help.github.com/articles/basic-writing-and-formatting-syntax/) 
                     [创始人John_Gruber](http://daringfireball.net/projects/markdown/syntax) 
                     [中文版](http://wowubuntu.com/markdown/index.html) 
                     [markdown+R](http://www.yangzhiping.com/tech/r-markdown-knitr.html)
* It can be easily converted to html, pdf, doc and so on.
* 更好的学习办法是直接读各类范本文件  by [阳志平](http://www.yangzhiping.com/tech/r-markdown-knitr.html)


### github (notes from [hello-world_guide](https://guides.github.com/activities/hello-world/))
* a website for version control, and collaboration
* the main characteristics include "repositories", "branches", "commits", and "pull requests"

1. Repositories
   * used to organize a single project
   * contains anything the project need, and a ``README.md``
2. Branches
   * used to work on different versions of a repository at one time
   * one branch named ``master`` is considered to be the definitive branch
   * anything in ``master`` should always be deployable
   * other branches are used to experiment and make edits before committing them to ``master``
   * when you create a branch off the ``master`` branch, you are making a copy, or a snapshot, of the ``master`` as it was at that point in time, and you can pull in others' updates on ``master`` afterwards.
   * when the change is ready, you can merge your branches into ``master``
3. Make and Commit Changes
   * **commits** are saved changes
   * each commit has an associated **commit message**, which explains why a particular change was made
4. Open and Merge a Pull Request
   * when you open a *pull request*, you are proposing your changes and requesing that someone review and pull in your contribution and merge them into their branch
   * the changes, addtions and subtractions, are shown in red and green
   * when the content is merged into ``master``, the branch can be deleted


### git guide (notes from websites)
* some websites I learned: [git-easy-guide](http://www.runoob.com/manual/git-guide/) 
              [5-minutes-git](http://www.runoob.com/w3cnote/git-five-minutes-tutorial.html) 
              
* git ssh-key 验证: 
   * 生成本地密钥:
         ``$ ssh-keygen -t rsa -C "youremail@email.com"``
   * 进入``~/.ssh/id_rsa.pub``, 复制该密钥, 粘贴至github帐户配置中
   * ssh-key验证成功后即可在本地利用git提交或合并修改内容
   
* commonly used Git command lines are summarized in [Git Cheat Sheet](https://github.com/HuangRuocheng/git-learning/blob/master/reference-files/).
   * `git clone [server-repo]`
   * `git add/rm` -> `git commit -m "comments"` -> `git push [alias] [local-branch]:[server-branch]`
   * `git branch [new-branch]` -> `git checkout [new-branch]` -> editing files in new-branch -> `git checkout [old-branch]` -> `git merge [new-branch]` -> `git branch -d [new-branch]`
   * `git push [alias] :[server-branch] ##delete server branch`
   * `git pull???`
