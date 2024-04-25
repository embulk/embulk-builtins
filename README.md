An umbrella repository to submodule built-in plugins.

```
git submodule add -b main https://github.com/embulk/embulk-<category>-<type>.git
```

```
git submodule update --init --recursive --remote
```

```
git submodule foreach 'if [ "$name" != "embulk-decoder-bzip2" ] && [ "$name" != "embulk-decoder-gzip" ]; then git checkout -b actions-macos-13; fi'
git submodule foreach 'if [ "$name" != "embulk-decoder-bzip2" ] && [ "$name" != "embulk-decoder-gzip" ]; then sed -i -e "s/^        \- macOS-latest/        \- macos-13  # OpenJDK 8 is not supported on macos-14+ (M1)./" .github/workflows/check.yml; fi'
git submodule foreach 'if [ "$name" != "embulk-decoder-bzip2" ] && [ "$name" != "embulk-decoder-gzip" ]; then git commit -a -m "Use macos-13 in GitHub Actions" || : ; fi'
git submodule foreach 'if [ "$name" != "embulk-decoder-bzip2" ] && [ "$name" != "embulk-decoder-gzip" ] && [ "$name" != "embulk-filter-remove_columns" ] ; then git push -u origin actions-macos-13 || : ; fi'`
git submodule foreach 'if [ "$name" != "embulk-decoder-bzip2" ] && [ "$name" != "embulk-decoder-gzip" ] ; then git checkout -b gradle-8.7 ; fi'
git submodule foreach 'if [ "$name" != "embulk-decoder-bzip2" ] && [ "$name" != "embulk-decoder-gzip" ] ; then ./gradlew wrapper --gradle-version=8.7 ; fi'
git submodule foreach 'if [ "$name" != "embulk-decoder-bzip2" ] && [ "$name" != "embulk-decoder-gzip" ] ; then git commit -a -m "Upgrade the Gradle wrapper to 8.7" || : ; fi'
git submodule foreach 'if [ "$name" != "embulk-decoder-bzip2" ] && [ "$name" != "embulk-decoder-gzip" ] ; then git push -u origin gradle-8.7 || : ; fi'
```
