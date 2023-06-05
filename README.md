A simple library to test pylibupdater.

# Release procedure
After a new commit, we need to create a new tag. To do so first get the last tag:

git fetch
git describe --tags --match "*.*" `git rev-list --tags --max-count=1`
Create a new one with bumping the last number: ( for example if last tag is v1.9)

git tag v1.10 -m "Bump version"
If this version is stable, make the major tag point to the last commit:

git tag -fa v1 -m "Update major tag"
Push the new commit:

git push origin main
Push the new tags:

# We need to force push v1 because it may exists if it's not the first major push.
git push origin v1.10
git push -f origin v1