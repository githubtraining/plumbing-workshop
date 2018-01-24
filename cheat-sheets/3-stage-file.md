# Staging the File

The index file is temporary, so let's create one by adding our file:

```
git update-index --add hello.md
OR
git update-index --add --cacheinfo 100644 557db03de997c86a4a028e1ebd3a1ceb225be238 hello.md
```

Let's look at it:

```
git ls-files --stage
```

### Jump to [Next Exercise](4-commit-file.md)
