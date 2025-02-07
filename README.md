# LavinMQ action

`cloudamqp/lavinmq-action` is a [composite run steps action] that starts LavinMQ in the GitHub Actions VM with the default guest/guest user/password. You can then connect to the broker using the address found in environment variable `AMQP_URL`.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: cloudamqp/lavinmq-action@main
    - run: <your test command>
```

[composite run steps action]: https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/creating-a-composite-run-steps-action
