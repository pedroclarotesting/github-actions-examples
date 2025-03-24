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

