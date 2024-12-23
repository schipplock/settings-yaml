# Settings YAML

`settings-yaml` ist eine Java Bibliothek, die Einstellungen in einer `YAML`-Datei
speichern und auch wieder auslesen kann.

## Installation

**Das muss in die pom.xml:**

```xml
<dependency>
    <groupId>de.schipplock.settings</groupId>
    <artifactId>settings-yaml</artifactId>
    <version>0.0.2</version>
</dependency>
```

## Wie verwende ich diese Bibliothek?

**Es wird folgender Import benötigt:**

```java
import de.schipplock.settings.YamlSettings;
```

**Einstellungen speichern:**

```java
var settings = YamlSettings.forUri(Path.of(System.getProperty("user.home"), "settings4223.yaml").toUri());
settings.setValue("language", "de");
settings.setValue("theme", "Monokai Pro");
settings.persist();
```

In `%USERPROFILE%\settings4223.yaml` (Windows) oder `$HOME/settings4223.yaml` (Linux) wurden die Einstellungen
gespeichert.

**Einstellungen lesen:**

```java
var settings = YamlSettings.forUri(Path.of(System.getProperty("user.home"), "settings4223.yaml").toUri());
settings.getValue("language");
settings.getValue("theme");
```

## License
[Apache License 2.0](https://choosealicense.com/licenses/apache-2.0/)