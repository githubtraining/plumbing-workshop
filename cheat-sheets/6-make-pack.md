# Create a Pack File

First, let's take a look at how many objects are in our repository:

```
git count-objects -H
```

Now let's pack it up:

```
git gc
```

Let's look again at the objects in our repository:

```
git count-objects -H
OR
git count-objects -v -H
```

Let's verify what is in the pack:

```
git verify-pack -v .git/objects/pack/pack-<pack-file>.idx
```

### Jump to [Next Exercise](7-second-branch.md)
