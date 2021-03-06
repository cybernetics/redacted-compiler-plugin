Releasing
=========

 1. Change the version in `gradle.properties` to a non-SNAPSHOT version.
 2. Update the `CHANGELOG.md` for the impending release.
 3. `git commit -am "Prepare for release X.Y.Z."` (where X.Y.Z is the new version)
 4. `git tag -a X.Y.Z -m "Version X.Y.Z"` (where X.Y.Z is the new version)
 5. `./gradlew clean && ./gradlew -p redacted-compiler-gradle-plugin clean uploadArchives -Dorg.gradle.parallel=false && ./gradlew uploadArchives -Dorg.gradle.parallel=false`
 6. `./gradlew closeAndReleaseRepository`
 7. Update the `gradle.properties` to the next SNAPSHOT version.
 8. `git commit -am "Prepare next development version."`
 9. `git push && git push --tags`
