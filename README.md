# test-lighthouse

## host

```shell
docker-compose build
docker-compose up -d
docker-compose exec lighthouse bash
```

## guest

### PC

```shell
lighthouse --only-categories=performance --output=html --output-path=report.html --emulated-form-factor=none --throttling-method=provided --chrome-flags="--headless --no-sandbox" https://www.google.co.jp/
```

### SP

```shell
userAgent="Mozilla/5.0 (iPhone; CPU iPhone OS 13_7 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) CriOS/85.0.4183.92 Mobile/15E148 Safari/604.1"
lighthouse --only-categories=performance --output=html --output-path=report.html --emulated-form-factor=none --throttling-method=provided --chrome-flags="--headless --no-sandbox --user-agent=\"${userAgent}\"" https://www.google.co.jp/
```

[Latest Safari on iOS User Agents](https://www.whatismybrowser.com/guides/the-latest-user-agent/safari)
