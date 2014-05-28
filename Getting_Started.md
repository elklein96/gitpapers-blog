#GitPapers
### A Blog Publishing Platform for Git

***

## Ready to make your first post?

GitPapers parses all files with a .md extension found in a user's `gitpapers-blog` repository on GitHub.

1. Create a new repository called `gitpapers-blog`

2. Clone the repository to your local directory

```
$ git clone http://github.com/username/gitpapers-blog
```

3. Create a new document in that directory

```
$ echo "This is my first blog post to GitPapers" > FirstPost.md
```

4. Add the document to the `gitpapers-blog` repository on GitHub

```
$ git add *
$ git commit -m "First blog post with GitPapers"
$ git push origin master
```

5. Go to your GitPapers page and read your first post!
