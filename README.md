# scalr-api

Scalr is a web-based control panel for cloud infrastructure that serves as an interface between end users and the multiple cloud platforms that they use. This Wercker step can be used to call your Scalr instance and manage your infrastructure. In other words, deploy that successful build already! Or whatever call you wish to perform. Works with hosted and open-source instances.

Link to API docs: https://scalr-wiki.atlassian.net/wiki/display/docs/API

# Options

* `endpoint` (required) Your Scalr API url
* `api-version` (required) The version of Scalr API that will be used
* `key-id` (required) The API Key ID
* `api-access-key` (required) The API Access Key
* `action` (required) The API action to be performed
* `params` (optional) All params. Must start with `&`. For example: &FarmID=1&ScriptID=2&ConfigVariables[a]=b

# Example

Add `SCALR_API_KEY_ID` & `SCALR_API_ACCESS_KEY` as deploy target or application environment variable.

```yaml
deploy:
  steps:
    - reneras/scalr-api:
        endpoint: http://yourserver.com/api/api.php
        api-version: 2.3.0
        key-id: $SCALR_API_KEY_ID
        api-access-key: $SCALR_API_ACCESS_KEY
        action: ScriptExecute
        params: &FarmID=1&ScriptID=2&ConfigVariables[a]=b
```

# License

The MIT License (MIT)
