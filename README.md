parent-pom
===

Just the parent POM, default information and such.


## Example Usage

Just drop this to your `pom.xml`:

````xml
    <parent>
        <groupId>xyz.luan</groupId>
        <artifactId>parent-pom</artifactId>
        <version>1.1.1</version>
    </parent>
````

## Config

In order to be able to deploy to oss.sonatype.org (Maven Central), you need the following `~/.m2/settings.xml` file:

```xml
<settings>
  <servers>
    <server>
      <id>sonatype-nexus-snapshot</id>
      <username>your username</username>
      <password>your password</password>
    </server>
    <server>
      <id>sonatype-nexus-staging</id>
      <username>your username</username>
      <password>your password</password>
    </server>
  </servers>
  <profiles>
    <profile>
      <id>deploy-gpg-singning</id>
      <activation>
        <activeByDefault>true</activeByDefault>
      </activation>
      <properties>
        <gpg.executable>gpg2</gpg.executable>
      </properties>
    </profile>
  </profiles>
</settings>
```

Your username and password are repeated twice (the same) and can be obteined on the [profile page](https://oss.sonatype.org/#profile;User%20Token) under `Access User Token`.

## Deploying

Unless you use the deploy profile, no signing is done and no key is needed. To deploy to maven central, use:

```bash
    mvn deploy -Pdeploy
```
