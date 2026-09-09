# Egor Loktev

I build open-source tools for practical AI-agent workflows.

## Artifact Relay

[Artifact Relay](https://github.com/eloktev/artifact-relay) is a private-by-default,
self-hosted gateway that turns long Markdown and standalone HTML agent outputs into
mobile-friendly pages.

- [Project website](https://artifact-relay.lok-labs.com/)
- [Self-host guide (~10 minutes after prerequisites)](https://artifact-relay.lok-labs.com/self-host/)
- [Hermes Agent plugin](https://github.com/eloktev/hermes-artifact-relay)

### Publish CI reports with GitHub Actions

If a workflow already produces a Markdown or standalone HTML report, the v1.3.0 composite action can
publish it without passing the relay token as an action input or command-line argument:

```yaml
- name: Publish report
  uses: eloktev/artifact-relay@v1.3.0
  env:
    ARTIFACT_RELAY_API_TOKEN: ${{ secrets.ARTIFACT_RELAY_API_TOKEN }}
  with:
    relay-url: https://artifacts.example.com
    artifact-path: build/report.md
```

[See the complete GitHub Actions guide](https://github.com/eloktev/artifact-relay#publish-a-ci-report-with-github-actions).
