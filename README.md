# Delete Comments

[![CodeQL](https://github.com/detomarco/delete-comment/actions/workflows/codeql-analysis.yml/badge.svg)](https://github.com/detomarco/delete-comment/actions/workflows/codeql-analysis.yml)

A GitHub action to delete an issue or pull request comments.

**NB: this action can only delete a comment by id at the moment. Feel free to open an issue or pull request if you would
like to delete comments based on other criterias**

## Usage

### Delete a comment of an issue or pull request

```yml
      - name: Delete comment
        uses: detomarco/delete-comment@v1
        with:
          token: ${GITHUB_TOKEN}
          repository: owner/repo
          comment-id: 231314915
```

### Action inputs

| Name         | Description                                                                                                                                                                   | Default            |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|
| `token`      | 'GITHUB_TOKEN' ('issues: write', 'pull-requests: write') or a repo scoped [PAT](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token). | 'GITHUB_TOKEN'     | 
| `repository` | The full name of the repository in which to create or update a comment.                                                                                                       | Current repository |
| `comment-id` | The id of the comment to delete.                                                                                                                                              |                    |

#### Outputs

| Name   | Description                                                     |
|--------|-----------------------------------------------------------------|
| `done` | `true` when the comment is found and deleted, `false` otherwise |

### How to find a comment id?

I recommend this github action [Find Comment](https://github.com/peter-evans/find-comment)

## License

[MIT](LICENSE)
