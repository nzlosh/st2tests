# st2tests

[![Build Status](https://circleci.com/gh/StackStorm/st2tests/tree/master.svg?style=shield)](https://circleci.com/gh/StackStorm/st2tests)

Congregation of all tests pertaining to release of st2 software.

## Running BATS tests

1. Make sure bats and other dependencies are installed

```bash
sudo apt-get install -y bats jq
```

2. Clone repo

```bash
git clone https://github.com/StackStorm/st2tests.git
```

3. Run tests or a specific test file

```bash
bats st2tests/cli/*.bats
bats st2tests/docs/*.bats
bats st2tests/chatops/*.bats
# or
bats st2tests/cli/test_execution_tail.bats
```

## Updating bundled subtrees

For example:

```bash
git subtree pull --prefix test_helpers/bats-assert https://github.com/ztombol/bats-assert.git master --squash
git subtree pull --prefix test_helpers/bats-support https://github.com/ztombol/bats-support.git master --squash
```

## Supported Python versions

StackStorm supports mulitple versions of python across numerous GNU/Linux distributions.  To define python dependencies in a
reproducible fashion, the `pip-compile` tool is used to resolve dependencies from the `requirements.in` file.  The requirements
are kept up to date with the `st2` repository and should be regenerated when requirements are updated.
