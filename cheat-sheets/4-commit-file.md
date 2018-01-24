# Committing the File

We are happy with our staging area, let's create the commit. First, we need to bundle up the tree:

```
git write-tree
```

Let's inspect the tree:

```
git cat-file -t a9f4f1b1c43c673f990eb51e2b3df18341d3f7bd
git cat-file -p a9f4f1b1c43c673f990eb51e2b3df18341d3f7bd
OR
git ls-tree a9f4f1b1c43c673f990eb51e2b3df18341d3f7bd 
```

But what is it really?

```
cat .git/objects/a9/f4f1b1c43c673f990eb51e2b3df18341d3f7bd
```

Let's add a commit object:

```
echo "initial commit" | git commit-tree a9f4f1b1c43c673f990eb51e2b3df18341d3f7bd
```

Another peek under the hood:

```
git cat-file -t <commit-SHA>
git cat-file -p <commit-SHA>
```

Let's take a look at `git status`:

```
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   hello.md
```

### Jump to [Next Exercise](5-make-branch.md)
