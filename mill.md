Here's an example of how to test a project with mill:

```bash
mill utest.jvm[2.12.8].test
```

- `utest.jvm` - the name of the compiled module (obtain from `build.sc`)
- `2.12.8` – Scala cross-compile version
- `test` – task to run on the module specified with the specified Scala version

To get mill of the most recent version:

```
# Adapted from: http://www.lihaoyi.com/mill/
sudo sh -c '(echo "#!/usr/bin/env sh" && curl -L https://github.com/lihaoyi/mill/releases/download/0.4.1/0.4.1-7-eeec02) > /usr/local/bin/mill && chmod +x /usr/local/bin/mill'
```

The recent version can be obtained from: https://github.com/lihaoyi/mill/releases