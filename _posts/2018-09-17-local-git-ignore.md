---
layout: post
title: 'How to ignore files locally in git'
date: 2018-09-17 08:00:00
comments: true
categories: development, git
---

Today I wanted to ignore some files locally while not dirtying the `.gitignore` file to avoid it appearing as a stageable change while running `git status`.

Possible solutions are explained in this [Stackoverflow thread][solutions] but are shown here verbatim:

> Do not forget, according to [gitignore][1], that there is an order of > precedence in the different "ignore pattern sources" that Git consider:
>
> - Patterns read from the command line for those commands that support them.
> - Patterns read from a .gitignore file in the same directory as the path, > or in any parent directory, with patterns in the higher level files (up to > the root) being overridden by those in lower level files down to the > directory containing the file.
> - Patterns read from `$GIT_DIR/info/exclude`.
> - Patterns read from the file specified by the configuration variable > `core.excludesfile`.
>
> The last two can be a solution for your problem but:
>
> - they are not replicated for a distant repository
> - they can have their patterns overridden by the other sources
>
> (See also this [SO question][2])
>
> ---
>
> The other two solutions involve updating the index ([`git update-index`][3]> ):
>
> - `git update-index --assume-unchanged`: see "[Git: untrack a file in > local repo only and keep it in the remote repo][4]".  
>   It is mentioned by [Elijah Lynn][5] in [the comments][6].
>   - You can even ignore a folder content: "[`git update-index > --assume-unchanged` on directory][7]".
>   - Use `--no-assume-unchange` to reverse the effect: See "[Is it possible > to `git add` a file currently protected by `assume-unchanged`?][8]".
>
> However, when you checkout another branch or when you `git pull`, that > "ignore" status might be reset. Hence the other option:
>
> - `git update-index --skip-worktree`; see:
>   - "[ignore my changes in files but don't delete them from remote rep][9]> " and
>   - "[Preserve git --assume-unchanged files between branch checkouts][10]".
>
> The difference between the two is explained in "[Git - Difference Between > '`assume-unchanged`' and '`skip-worktree`'][11]".
>
> [1]: http://git-scm.com/docs/gitignore
> [2]: > https://stackoverflow.com/questions/640449/git-dont-show-me-pyc-in-the-li> st-of-untracked-files/640668#640668
> [3]: http://git-scm.com/docs/git-update-index
> [4]: https://stackoverflow.com/a/6793752/6309
> [5]: https://stackoverflow.com/users/292408/elijah-lynn
> [6]: > https://stackoverflow.com/questions/653454/how-do-you-make-git-ignore-fil> es-without-using-gitignore/653495#comment39345310_653495
> [7]: https://stackoverflow.com/a/12288918/6309
> [8]: https://stackoverflow.com/a/23189283/6309
> [9]: https://stackoverflow.com/a/23011156/6309
> [10]: https://stackoverflow.com/a/9816844/6309
> [11]: https://stackoverflow.com/q/13630849/6309

I ended up using the `$GIT_DIR/info/exclude` option.

[solutions]: https://stackoverflow.com/a/653495/182153
