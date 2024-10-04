
# Git Tagging and Releases

## 1. Create an Annotated Tag
Tags are used to mark specific points in history. To create an annotated tag (which includes a message and metadata), use:
```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
```

**Explanation:** This creates a tag `v1.0.0` with a message. Annotated tags are stored as full objects in the Git database.

## 2. Push Tags to Remote
By default, tags are not pushed to the remote. To push a tag, use:
```bash
git push origin <tag-name>
```

You can also push all tags at once with:
```bash
git push origin --tags
```

**Explanation:** This pushes the tags to the remote repository.

## 3. Lightweight Tags
Lightweight tags are just pointers to specific commits without additional metadata. Create a lightweight tag with:
```bash
git tag v1.0.0
```

**Explanation:** Lightweight tags are quick references and don’t store extra information like messages or the tagger’s identity.

## 4. List Tags
To view all tags in your repository, use:
```bash
git tag
```

**Explanation:** This lists all tags, allowing you to check what versions have been tagged.

## 5. Checkout a Tag
To switch to a specific tag (in detached HEAD state):
```bash
git checkout <tag-name>
```

**Explanation:** This lets you view the project at the point in time when the tag was created.

[Back to README](../README.md)
    