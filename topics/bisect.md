
# Git Bisect for Debugging

## 1. What is Git Bisect?
`git bisect` is a powerful tool that helps you find the commit that introduced a bug by using binary search.

## 2. Start Bisecting
To begin bisecting, first tell Git which commit is good and which commit is bad. Navigate to a known bad commit and a known good commit:
```bash
git bisect start
git bisect bad <bad-commit-hash>
git bisect good <good-commit-hash>
```

**Explanation:** This starts the bisect process and tells Git that the bug is present in the `<bad-commit-hash>` and not present in the `<good-commit-hash>`.

## 3. Test Each Commit
Git will now check out a commit halfway between the good and bad commits. Test the code and if the bug is present, mark the commit as bad:
```bash
git bisect bad
```

If the bug is not present, mark the commit as good:
```bash
git bisect good
```

Git will continue narrowing down the commits until it finds the one that introduced the bug.

## 4. Reset After Bisecting
Once you've found the commit that introduced the bug, reset to your original state:
```bash
git bisect reset
```

**Explanation:** This restores your working directory to the state before you started bisecting.

## 5. Automating Git Bisect
You can automate the bisect process by passing a test script that exits with status 0 if the code is good, and non-zero if it's bad:
```bash
git bisect run <test-script>
```

**Explanation:** This runs the specified script at each step of the bisect, saving you the trouble of manually testing.

[Back to README](../README.md)
    