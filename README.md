# renovate-composer-path
test repository to reproduce renovatebot issue

On first run, it can be seen that dependency is not resolved
https://app.renovatebot.com/dashboard#github/bburnichon/renovate-composer-path/462508112

```
DEBUG: packageFiles with updates
{
  "config": {
    "composer": [
      {
        "packageFile": "composer.json",
        "deps": [
          {
            "depType": "require",
            "depName": "bburnichon/subrepo",
            "currentValue": "*@dev",
            "datasource": "packagist",
            "depIndex": 0,
            "updates": [],
            "warnings": [
              {
                "topic": "bburnichon/subrepo",
                "message": "Failed to look up dependency bburnichon/subrepo"
              }
            ],
            "versioning": "composer"
          }
        ],
        "registryUrls": [
          "https://packagist.org"
        ],
        "managerData": {
          "composerJsonType": "project"
        }
      }
    ]
  }
}
```
