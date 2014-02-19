# Résumé

Here are the LaTeX files for my résumé. You can see a recent pdf version on my site: [jelv.is/resume.pdf](jelv.is/resume.pdf).

For this iteration, I didn't use a template—I just designed everything from the ground up. (Not that there's all that much actual design involved!) I think the GitHub icon is cute :).

If you like parts of the design, feel free to use them yourself. I've released everything under a BSD licence. The main file is `resume.ltx`; it includes and compiles all the relevant sections. Some of the unused section files are not up to date.

The actual résumé breaks a bunch of rules people give you for writing résumés. Meh. The biggest problem is that it takes two pages rather than one: I should go through and remove a bunch of detail from each of the experience bullet points, but I really don't feel like it.

I'll probably create a more compact version at some point.

## Customization

The header details are stored in a bunch of variables in `resume.sty`. You should be able to customize them using `renewcommand`:

    \renewcommand{\name}{Tikhon Jelvis}
    \renewcommand{\addr}{1100 Pine St., Menlo Park, CA 94025}
    \renewcommand{\phoneNumber}{(650) 283-4713}
    \renewcommand{\email}{tikhon@jelv.is}
    \renewcommand{\major}{EECS}
    \renewcommand{\university}{University of California, Berkeley}
    \renewcommand{\degree}{BS}
    \renewcommand{\website}{\url{http://jelv.is}}
    \renewcommand{\github}{\url{http://github.com/TikhonJelvis}}

You can then rewrite each section or just `\input` new files in `resume.ltx` instead. It's pretty straightforward.

`resume.sty` defines a bunch of useful commands. `\rsec{Section Title}` starts a new section (like "Experience" or "Publications").

Each entry is introduced with an `\entry{Title}{Sub-title}` or `\work{Title}{Start date}{End date}` command. The only real difference is that `\work` formats the dates for you. Both of these commands expect to be inside an `enumerate` or `itemize` environment!

There is a special `experience` environment. This holds the details for each entry in an implicit `itemize` (so you have to use `\item` inside it). This just formats the list of bullet points correctly.

Finally, the `\header` command actually inserts the header. You should have it at the top of your file.