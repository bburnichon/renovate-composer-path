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

On this repository, it is not really relevant but on real cases, specific requirements for sub-repos could change dependencies.

Afterwards, I added a repository with fully qualified path and package is also not resolved correctly.

https://getcomposer.org/doc/05-repositories.md

https://app.renovatebot.com/dashboard#github/bburnichon/renovate-composer-path/462508331

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
            "depName": "bburnichon/full-path",
            "currentValue": "*@dev",
            "datasource": "packagist",
            "depIndex": 0,
            "updates": [],
            "warnings": [
              {
                "topic": "bburnichon/full-path",
                "message": "Failed to look up dependency bburnichon/full-path"
              }
            ],
            "versioning": "composer"
          },
          {
            "depType": "require",
            "depName": "bburnichon/subrepo",
            "currentValue": "*@dev",
            "datasource": "packagist",
            "depIndex": 1,
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
