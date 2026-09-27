# Robin Custom Headers

Modified Robin action with custom header support for OpenCode Zen API (big-pickle).

## Usage

```yaml
- name: Robin review
  uses: Xiaobei09/robin-custom-headers@main
  with:
    github-token: ${{ github.token }}
    llm-api-key: public
    llm-base-url: https://opencode.ai/zen/v1
    model: big-pickle
    custom-headers: '{"x-opencode-session":"ses_xxx"}'
    config-file: .github/robin.yml
    review-instructions-file: .github/code-reviewer.md
    min-command-permission: none
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| github-token | GitHub token for posting PR review comments | true | ${{ github.token }} |
| llm-api-key | API key for your LLM endpoint | false | ollama |
| llm-base-url | Base URL for OpenAI-compatible API | true | - |
| model | Model name to use | true | - |
| custom-headers | Optional JSON object with custom headers | false | "" |
| config-file | Repository config file | false | .github/robin.yml |
| review-instructions-file | Reviewer instructions file | false | .github/code-reviewer.md |
| min-command-permission | Minimum permission for slash commands | false | write |

## Custom Headers

The `custom-headers` input allows you to pass additional headers to the LLM API. This is useful for:

- OpenCode Zen API: `{"x-opencode-session":"ses_xxx"}`
- Custom authentication headers
- Additional metadata headers

## License

MIT
