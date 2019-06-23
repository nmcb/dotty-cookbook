Here's an example of how to test a project with mill:

```bash
mill utest.jvm[2.12.8].test.test
```

To compile test sources:

```bash
mill utest.jvm[2.12.8].test.compile
```

To get mill of the most recent version:

```
# Adapted from: http://www.lihaoyi.com/mill/
sudo sh -c '(echo "#!/usr/bin/env sh" && curl -L https://github.com/lihaoyi/mill/releases/download/0.4.1/0.4.1-7-eeec02) > /usr/local/bin/mill && chmod +x /usr/local/bin/mill'
```

The recent version can be obtained from: https://github.com/lihaoyi/mill/releases