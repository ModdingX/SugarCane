# SugarCane

SugarCane is a gradle script to sanitize [Parchment](https://github.com/ParchmentMC/Parchment) mappings using [SourceTransform](https://github.com/ModdingX/SourceTransform).

This will remove the leading `p` whenever possible and also keep lambda parameters.

## How to use

To use SugarCane, add the following to your `build.gradle`:

Inside the `buildscript block`:
```groovy
repositories {
    maven { url = 'https://maven.parchmentmc.org' }
    maven { url = 'https://maven.moddingx.org' }
}

dependencies {
    classpath 'org.parchmentmc:librarian:<librarian_version>'
    classpath 'org.moddingx:ModGradle:<modgradle_version>'
}
```

Replace `<modgradle_version>` with the version of ModGradle to use. See [here](https://maven.moddingx.org/org/moddingx/ModGradle).

Right after the line `apply plugin: 'net.minecraftforge.gradle'`:

```groovy
apply plugin: 'org.moddingx.modgradle.mapping'
```

You can then use the mapping channel `sugarcane`. A list of versions can be found [here](https://maven.moddingx.org/org/moddingx/sugarcane).

Example:

```groovy
mappings channel: 'sugarcane', version: '2021.09.05-1.17.1'
```

### ModUtils

If you use [ModUtils](https://github.com/ModdingX/ModUtils), you don't need to apply any extra plugins, you can just use the `sugarcane` channel.
