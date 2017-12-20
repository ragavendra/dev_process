## dev_process
Development process for building apps

### Development steps

1. Fork the project
2. Checkout `dev` branch (`git checkout dev`)
3. Create your `feature` branch (`git checkout -b my-new-feature`)
4. Add and commit your changes (`git commit -am 'Add some feature'`)
5. Push feature branch (`git push origin my-new-feature`)
6. Create new Pull Request on Github.com against `dev` branch and assign it to `Raga`

### Development process

1. Branch from `dev`
2. Do work
3. Open PR against `dev`
3.1 Once PR is approved and merged
4. Merged to `dev` by `Raga`

### Release process

1. Branch from `dev` to update `CHANGELOG.md` to include the commit hashes and release date
2. Update the `version` constant in `constants/version.go` following [semver](http://semver.org/)
3. Merge to `dev`
4. Tag the master branch with the release:
```bash
   git tag vX.Y.Z or vX.Y.Z-alpha.N or vX.Y.Z-beta.N
   git push origin vX.Y.Z
```
5. Merge to `dev` to release to stable/beta/dev
6. Add release to Github [release page](https://github.com/ragavendra/continuous_integration/releases)

#### Versioning
Check the `circle.yml` for the latest, but currently merging to master will build and deploy to the following Equinox channels:

Tag                             | Channels
--------------------------------|-------------
No tag                          | dev
vX.Y.Z-alpha.N or vX.Y.Z-beta.N | beta, dev
vX.Y.Z                          | stable, beta, dev
