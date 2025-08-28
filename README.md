# LavinMQ action

`cloudamqp/lavinmq-action` is a [composite run steps action] that starts LavinMQ in the GitHub Actions VM with the default guest/guest user/password. You can then connect to the broker using the address found in environment variable `AMQP_URL`.

This action is stable, so you can use `cloudamqp/lavinmq-action@main` to always get the latest updates.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: cloudamqp/lavinmq-action@main
    - run: <your test command>
```

You can customize the environment variable name and the LavinMQ version used:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: cloudamqp/lavinmq-action@v1
      with:
        env-key: LAVINMQ_URL
        version: 2.4.1
    - run: <your test command>
```

[composite run steps action]: https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/creating-a-composite-run-steps-action
