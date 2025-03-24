# github-actions-examples


Testing different concepts from GitHub Actions Docs.

Organized by branches

## Projects

### Secrets

Testing GitHub secrets

|workflow |description | outcome|
| --- | --- | --- |
|secrets-if.yaml| Tests if secret is "known"| Secret was imported; comparisons with strings to reveal secrets does not work (,as expected).|

### Events

Testing different types of events

|workflow |description | outcome|
| --- | --- | --- |
|events-cron.yaml |alerts every 5 minutes (currently disabled)| does not work reliably due to GitHub limitations. |
|events-issues.yaml|alerts on new issues| This type of event works only on main branch, not sure why yet.|

### Matrix

|workflow |description | outcome|
| --- | --- | --- |
|matrix-os-and-random-numbers.yaml |Tests using different OS, using the including and excluding functions from matrices, and adding special variables not available in all combinations| works! |

### Concurrency
|workflow |description | outcome|
| --- | --- | --- |
|concurrence-create-file| creates file and stores it in artifact| worked:)|
|concurence-modify-file1 and 2 | triggered on create file workflow end and gets artifact (using PAT and run id from event), adds a line; they work one at a time | the first one starting stops the other until finished; but both pull the same file (explained below)|
|concurrence-read-file | reads files after updated from modify-file.| since both concurrence-modify-file 1 and 2 created different artifacts, they end up producing two files. To fix this it would make more sense to use a shared cloud storage or find a way for the first modifier to finish to give runner_id to second (allowing them to trigger each other is not a solution as it causes a loop, needs furhter testing)