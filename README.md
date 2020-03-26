# Composer No Download Packages
This plugin prevents composer to download packages, but let him update composer.lock with correct infos.

This is useful in CI/CD pipelines, where you need to just update the composer.lock file, but you're not interested in
having PHP libraries be physically installed in your /vendor folder.

### Installation
```$sh
composer require adamamont/composer-no-download
```

Use env variable COMPOSER-NO-DOWNLOAD with value "apply" for plugin activation

Example (Jenkins pipeline)

```$groovy
withEnv(["COMPOSER-NO-DOWNLOAD=apply"]) {
    sh "composer update"
}
```

Thanks [@edubacco](https://github.com/edubacco) for solution

