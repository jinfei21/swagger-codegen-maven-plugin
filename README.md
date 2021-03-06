swagger-codegen-maven-plugin
============================

[![Build Status](https://travis-ci.org/garethjevans/swagger-codegen-maven-plugin.svg?branch=master)](https://travis-ci.org/garethjevans/swagger-codegen-maven-plugin)
[![Maven version][maven-img]][maven-url]

A Maven plugin to support the [swagger](http://swagger.io) code generation project

Usage
============================

Add to your `build->plugins` section (default phase is `generate-sources` phase)
```xml
<plugin>
    <groupId>com.garethevans.plugin</groupId>
    <artifactId>swagger-codegen-maven-plugin</artifactId>
    <version>${project.version}</version>
    <executions>
        <execution>
            <goals>
                <goal>generate</goal>
            </goals>
            <configuration>
                <inputSpec>src/main/resources/api.yaml</inputSpec>
                <language>java</language>
            </configuration>
        </execution>
    </executions>
</plugin>
```

Followed by:

```
mvn clean compile
```

### Configuration parameters

- `inputSpec` - swagger spec file path
- `language` - target generation language
- `output` - target output path (default is `${project.build.directory}/generated-sources/swagger`)
- `templateDirectory` - directory with mustache templates
- `addCompileSourceRoot` - add the output directory to the project as a source root (`true` by default)

-- 
[maven-url]: https://search.maven.org/#search%7Cga%7C1%7Cswagger-codegen-maven-plugin
[maven-img]: https://img.shields.io/maven-central/v/com.garethevans.plugin/swagger-codegen-maven-plugin
