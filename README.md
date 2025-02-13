# renovate-reproduction-34204
Minimal reproduction of problem raised in [discussion 34204](https://github.com/renovatebot/renovate/discussions/34204) in renovate repo

## Current behaviour ##

Renovate creates then closes its update pull-requests, based on a customManager/customDatasources using a public API endpoint.
This is probably because it raises lookup errors in its scan log
```
DEBUG: GET https://api.github.com/repos/protocolbuffers/protobuf/releases = (code=ERR_NON_2XX_3XX_RESPONSE, statusCode=403 retryCount=0, duration=4)
DEBUG: Failed to look up custom.protoc package protoc
{
  "dependency": "protoc"
  "packageFile": ".protoc-version"
}
```

## Expected behaviour ##

No more `403` errors when doing the scan of the repo on this customManager


