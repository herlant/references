# references
Bibtex reference files. The main file ``master.bib`` includes all references, while ``longnames.bib`` and ``shortnames.bib`` include full and abbreviated conference/journal names, respectively.

To use short name abbreviations in your `.tex` file, use
```
\bibliography{refs/shortnames,refs/master}
```

To use long names in your `.tex` file, use
```
\bibliography{refs/longnames,refs/master}
```

## Creating a submodule
The best way to use this repository is as a submodule to another Git repository that contains your `.tex` files. See this helpful blog post for [an introduction to using submodules for BibTeX references](http://andrius.velykis.lt/2012/06/master-bibtex-file-git-submodules/), or get more [detailed information about submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules). 

To add this repository as a submodule, `cd` into the Git directory with your LaTeX files, then run
```
git submodule add https://git.personalrobotics.ri.cmu.edu/lcv/references.git refs
```
This will create a `refs` subdirectory that links to this repository.

## Cloning a repository with a submodule
You can clone a repository that contains a submodule and pull all of the submodule data at once by adding the `--recursive` tag:
```
git clone --recursive REPO_ADDRESS
```

If you've already cloned a repository that links to this submodule without using the `--recursive` tag, you'll have the directory that points to this repo but it will be empty. To initialize and populate the submodule, run
```
git submodule init # initializes the local configuration file
git submodule update # fetches data from the appropriate commit
```

## Getting most recent version of submodule
If there are changes made to the references that you want to pull into a separate git repo, but you've already set it up with the submodule, you can get the newest version, by
```
git submodule update --remote
```
