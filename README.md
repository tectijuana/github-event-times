# github-event-times.py 

This program uses the GitHub "Events" API to print all of the *push*
times for each commit, with its output in LaTeX "tabular" format. This
might be useful if you have a student who you suspect of falsifying
commit times around a deadline and you need to document what happened.

## Installation


1) If you haven't already done this, you'll first need to `pip install
requests` for a necessary library.

2) Get a GitHub token with all the "Repo" privileges. You do
this on the GitHub website
[(instructions)](https://github.com/blog/1509-personal-api-tokens). 

3) Optionally, edit the `defautGithubProject` variable to reflect your
   project's name (e.g., for `https://github.com/RiceComp215`, the
   project name is `RiceComp215`). You can also install your GitHub
   API token in the `defaultGithubToken` variable.

## Usage

Now let's say you want to get the commit times for a series of repos
with
names like assignment3-student1 and assignment3-student2, 
you can simply run `python github-event-times.py assignment3-student1
assignment3-student2`
and it will print a table with the commit IDs (7 digit prefix, same
as reported on GitHub's list of commits), the commit string, and the
time at which that commit was pushed to GitHub. Note that times are
reported in [RFC 3339](https://www.ietf.org/rfc/rfc3339.txt) style,
which is UTC, so you may wish to adjust this to your local time.

```
Example

ccitt@ccitt:~/github-event-times$ python github-event-times.py g410b1-markdown-mesa-3-pijamas-en-llamas
Events for g410b1-markdown-mesa-3-pijamas-en-llamas

\begin{tabular}{lll}
{\bf Commit ID} & {\bf Comment} & {\bf GitHub push time} \\
\hline
0848e3d & Update README.md & 2019-03-04T18:25:33Z \\
060dcf6 & Update README.md & 2019-03-04T18:22:41Z \\
e04156a & Set theme jekyll-theme-merlot & 2019-02-27T16:41:28Z \\
b1e0884 & Set theme jekyll-theme-time-machine & 2019-02-27T16:41:16Z \\
be33543 & Set theme jekyll-theme-minimal & 2019-02-27T16:41:04Z \\
66d13e3 & Set theme jekyll-theme-minimal & 2019-02-27T16:39:55Z \\
79166a7 & Set theme jekyll-theme-minimal & 2019-02-27T16:39:14Z \\
ba90dac & Set theme jekyll-theme-merlot & 2019-02-27T16:36:50Z \\
09c6629 & Update README.md & 2019-02-27T15:58:08Z \\
1d4b0cf & Update README.md & 2019-02-25T19:40:37Z \\
776a878 & Update antimalware.md & 2019-02-25T19:21:37Z \\
b55641f & Update companias.md & 2019-02-25T19:21:21Z \\
0b65ddc & Update tipos.md & 2019-02-25T19:20:49Z \\
17e7846 & Update antecedentes.md & 2019-02-25T19:19:58Z \\
b30f7f2 & Update README.md & 2019-02-25T19:16:47Z \\
9dafcba & Update README.md & 2019-02-25T19:15:28Z \\
0b97a4d & Update README.md & 2019-02-25T19:08:30Z \\
7ef7c8a & Update README.md & 2019-02-25T19:06:51Z \\
3871440 & Update companias.md & 2019-02-25T19:06:27Z \\
f1e9d05 & Update antimalware.md & 2019-02-25T19:06:00Z \\
e866ab7 & Update antimalware.md & 2019-02-25T19:04:58Z \\
2753252 & Update tipos.md & 2019-02-25T19:01:31Z \\
8d86811 & Update antecedentes.md & 2019-02-25T19:01:12Z \\
26103c6 & Update README.md & 2019-02-25T18:58:11Z \\
b4bc6f0 & Update README.md & 2019-02-25T18:56:12Z \\
4291e30 & Update README.md & 2019-02-25T18:55:54Z \\
04b2b64 & Update README.md & 2019-02-25T18:48:49Z \\
\hline
\end{tabular}
```
