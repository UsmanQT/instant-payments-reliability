# Experiments

Each experiment answers one question and runs the same way every time.

## Layout

```
experiments/
  E01-short-name/
    README.md      hypothesis, setup, procedure, expected and actual results (from _template.md)
    run.*          script that runs the experiment from a clean state
    reports/       output from each run, named by date and git commit
```

## Rules

1. Write the hypothesis and expected result **before** running the experiment.
2. Record the git commit, target system (`baseline` or `payments-lab`), parameters and random seed for every run.
3. Keep raw output. A result is **verified** only if it can be reproduced from this repository.
4. Report surprising and negative results the same way as expected ones.

## Index

| ID | Question | Target | Status | Result |
|---|---|---|---|---|
| E01 | Does a retry after a crash between charge and recovery point double-charge? | baseline | planned | — |
