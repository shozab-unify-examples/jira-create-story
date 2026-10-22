# ADP Jira Create Story Action

Creates a Jira Cloud Story using ADP's mandatory description structure:

1. Title
2. User Story
3. Context & Scope
4. Acceptance Criteria

It also applies the Jira option IDs validated during the POC for `Blocked`, `Bypass Gating Rules`, and `Story Type`.

## Example

```yaml
- name: Create ADP Jira Story
  id: create-story
  uses: https://bitbucket.org/adp-uat/adp-jira-create-story@v1.0.0
  with:
    jira-url: https://adp-uat.atlassian.net
    jira-email: ${{ secrets.JIRA_EMAIL }}
    jira-api-token: ${{ secrets.JIRA_API_TOKEN }}
    project-key: ONECICD
    summary: CloudBees Unify Jira integration validation
    title: Validate CloudBees Unify Jira integration
    user-story: As a OneCICD platform engineer, I want Unify to create compliant Jira Stories so that delivery activity remains traceable.
    context-and-scope: Validate Jira Story creation from a CloudBees Unify workflow.
    acceptance-criteria: The Story is created, the ADP template is accepted, and the issue key is returned to the workflow.
```

## Outputs

```text
issue-key
issue-id
issue-url
```

