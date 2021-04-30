# Hello world javascript action

This action prints "Hello World" or "Hello" + the name of a person to greet to the log.

## Description

This action will read your name and the event's payload, and print it on the Github MV's console. Also, it will return the time the action was executed as an output. 

## Inputs

### `who-to-greet`

**Required** The name of the person to greet. Default `"World"`.

**Optional** None

## Outputs

### `time`

**Required** None

**oPtional** The time we greeted you.

## Secrets

None

## Environment variables required

None

## Example usage

```yml
name: Using hello world
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      # To use this repository's private action, you must check out the repository
      - name: Checkout
        uses: actions/checkout@v2
      - name: Hello world action step
        uses: ULL-ESIT-PL-2021/hello-js-action-alu0101240374@v1
        id: hello
        with:
          who-to-greet: 'Gabriel'
      # Use the output from the `hello` step
      - name: Get the output time
        run: echo "The time was ${{ steps.hello.outputs.time }}"
```

## Example output