# Creating a File

Let's try this from two different directions. First, let's create the object directly:

```
echo "Hello World" | git hash-object --stdin -w
```

Now, let's create a file and then the object:

```
echo "Hello World" > hello.md
git hash-object -w hello.md
```

Let's look under the hood:

```
git cat-file -t <hash>
git cat-file -p <hash>
git cat-file -s <hash>
```

How do we know this is a hash of the content of the file?

```
printf "blob 12\000Hello World\n" | openssl sha1
OR
printf "blob 12\000Hello World\n" | shasum
```

But what is actually in the file?

```
cat .git/objects/55/7db03de997c86a4a028e1ebd3a1ceb225be238
```

Borrowing brains (thank you @matthewmccullough), let's decipher it:

```
alias deflate="perl -MCompress::Zlib -e 'undef $/; print uncompress(<>)'"
deflate .git/objects/55/7db03de997c86a4a028e1ebd3a1ceb225be238
```

### Jump to [Next Exercise](3-stage-file.md)
