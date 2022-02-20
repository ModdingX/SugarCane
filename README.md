# SugarCane

SugarCane is a gradle script to sanitize [Parchment](https://github.com/ParchmentMC/Parchment) mappings using [SourceTransform](https://github.com/noeppi-noeppi/SourceTransform).

This will remove the leading `p` whenever possible and also keep lambda parameters.

## How to use

To use SugarCane, add the following to your `build.gradle`:

Inside the `buildscript block`:
```groovy
repositories {
    maven { url = 'https://maven.parchmentmc.org' }
    maven { url = 'https://noeppi-noeppi.github.io/MinecraftUtilities/maven' }
}

dependencies {
    classpath 'org.parchmentmc:librarian:<librarian_version>'
    classpath 'io.github.noeppi_noeppi.tools:ModGradle:<modgradle_version>'
}
```

Replace `<modgradle_version>` with the version of ModGradle to use. See [here](https://github.com/noeppi-noeppi/MinecraftUtilities/tree/master/maven/io/github/noeppi_noeppi/tools/ModGradle).

Right after the line `apply plugin: 'net.minecraftforge.gradle'`:

```groovy
apply plugin: 'io.github.noeppi_noeppi.tools.modgradle.mapping'
```

You can then use the mapping channel `sugarcane`. A list of version can be found [here](https://maven.melanx.de/io/github/noeppi_noeppi/sugarcane).

Example:

```groovy
mappings channel: 'sugarcane', version: '2021.09.05-1.17.1'
```

### ModUtils

If you use [ModUtils](https://github.com/noeppi-noeppi/ModUtils), you don't need to apply any extra plugins, you can just use the `sugarcane` channel.