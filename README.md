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

## Deploying

Unless you use the deploy profile, no signing is done and no key is needed. To deploy to maven central, use:

```bash
    mvn deploy -Pdeploy
```
