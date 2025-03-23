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
|events-cron.yaml |alerts every minute between 11pm and midnight on sunday| does not work reliably even using yaml from docs. Might be unreliable. |
|events-issues.yaml|alerts on new issues| This type of event works only on main branch, not sure why yet.|

### Matrix