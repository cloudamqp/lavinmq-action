# LavinMQ action

`cloudamqp/lavinmq-action` is a [composite run steps action] that starts [LavinMQ](https://lavinmq.com/) in the GitHub Actions VM with the default guest/guest user/password. You can then connect to the broker using the address found in environment variable `AMQP_URL`.

This action is stable, so you can use `cloudamqp/lavinmq-action@main` to always get the latest updates.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: cloudamqp/lavinmq-action@main
    - run: <your test command>
```

You can customize the environment variable name, the LavinMQ version, and optionally create a vhost:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: cloudamqp/lavinmq-action@v1
      with:
        env-key: LAVINMQ_URL
        version: 2.6.9
        vhost: my-vhost
    - run: <your test command>
```

| Input | Description | Default |
|-------|-------------|---------|
| `env-key` | Name of the environment variable with the LavinMQ URL | `AMQP_URL` |
| `version` | The version of LavinMQ to install | `latest` |
| `vhost` | Name of a vhost to create in the broker (included in the AMQP URL) | _(none)_ |

[composite run steps action]: https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/creating-a-composite-run-steps-action
