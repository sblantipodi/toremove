This guide is for developers building **Firefly Luciferin** from source. For a normal installation, use [Installers and binaries](https://github.com/sblantipodi/firefly_luciferin/wiki/Installers-and-binaries).

## Requirements

The current `pom.xml` targets **Java 25**. Use a matching JDK and Maven, plus Git. Native dependencies and packaging tools vary with the operating system and architecture.

The Maven profiles select platform specific desktop dependencies for Windows, Linux x86-64, and Linux ARM64. Build for the system on which the application will run.

## Build Firefly Luciferin from source

Clone the repository with its packaging submodules:

```bash
git clone --recurse-submodules https://github.com/sblantipodi/firefly_luciferin.git
cd firefly_luciferin
mvn clean package
```

For an existing checkout, initialize missing submodules before building:

```bash
git submodule update --init --recursive
```

The build produces the application artifacts under **target**, including `FireflyLuciferin-jar-with-dependencies.jar`. Running the assembled JAR also requires the appropriate native media libraries and JVM options; the packaged installer supplies a configured launcher.

## Create Firefly Luciferin binary installer for Windows/Linux

Firefly uses the JDK's **jpackage** tool. Installer creation includes more than wrapping a JAR:

- Platform resources, icons, and native media dependencies.
- JVM options for the Vector API and native access.
- Windows WiX tooling or Linux DEB/RPM packaging tools.
- Architecture specific dependencies and package naming.

Use the commands and preparation steps from the workflow corresponding to your build rather than an older standalone jpackage command:

- [Development build workflow](https://github.com/sblantipodi/firefly_luciferin/blob/master/.github/workflows/build.yml).
- [Repository workflows](https://github.com/sblantipodi/firefly_luciferin/tree/master/.github/workflows) for release and architecture specific packaging.
- [Maven configuration](https://github.com/sblantipodi/firefly_luciferin/blob/master/pom.xml) for compiler options and dependencies.

Workflow variables such as the release version must be replaced with concrete local values. A step's historical label mentioning “Java 14 Package API” does not change the current Java 25 requirement.

## Building Glow Worm Luciferin firmware

Firmware is a separate project built with **PlatformIO**. Clone [Glow Worm Luciferin](https://github.com/sblantipodi/glow_worm_luciferin), select the environment for your board and firmware variant, and build from that repository:

```bash
pio run -e YOUR_ENVIRONMENT
```

Use its `platformio.ini` and firmware build workflows to identify the correct environment. A Firefly application build does not build or flash the controller firmware.
