get-commit-files, a GitHub Action by Irving Decarlo

# What is the Action for?

get-commit-files is an Action that is capable of getting a specific file type from commits that are part of a GitHub event, such as a push. With it, you are capable of getting all files that were modified or created within said event.

> [!IMPORTANT]
> Not all GitHub event were tested, only with push actions.

## How to use

It can be used freely by any workflow. It requires 4 parameters:
1. `commits-json`: The `github.event.commits` property but as a JSON:
```
commits-json: ${{ toJson(github.event.commits) }}
```
2. `git-branch`: The GitHub branch that invoked the event:
```
git-branch: ${{ github.ref_name }}
```
3. `file-type`: The file type that you want to filter:
```
file-type: ".txt"
```
4. `file-ignore`: The file to signal that all files under a specific folder are to be ignored:
```
file-ignore: ".fileignore"
```

And it outputs:
1. `modified-files`: A comma-separated list of modified files.

## Roadmap

- [x] File Filtering
- [x] File Ignoring
- [ ] Filter multiple file types
- [ ] Test other GitHub actions

## How can I contribute

Feel free to give me any suggestions that you believe will improve the Action. Additionally, you may make your own Action that is based on this one.

Thank you!
