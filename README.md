# Pizzabyte Images

Docker images designed for use with Pterodactyl's Egg system. Modified for Pizzabyte.

## [Java](/java)

These images are running the Java software at a specified version. You can switch a server from running one version to another version without any issues.

Currently built versions with their vendors are Eclipse Temurin, IBM Semeru, and GraalVM CE. Only LTS versions are provided.

> [!NOTE]
>
> Make sure of which image you use, as performance and stability can vary between vendors. We recommend Eclispe Temurin as the best baseline for any Java-based image.

* [`java8`](/java/8/)
  * [`java8-temurin`](/java/8/temurin/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_8-temurin`
  * [`java8-semeru`](/java/8/semeru/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_8-semeru`
  * [`java8-graalvm`](/java/8/graalvm/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_8-graalvm`
* [`java11`](/java/11/)
  * [`java11-temurin`](/java/11/temurin/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_11-temurin`
  * [`java11-semeru`](/java/11/semeru/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_11-semeru`
  * [`java11-graalvm`](/java/11/graalvm/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_11-graalvm`
* [`java17`](/java/17/)
  * [`java17-temurin`](/java/17/temurin/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_17-temurin`
  * [`java17-semeru`](/java/17/semeru/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_17-semeru`
  * [`java17-graalvm`](/java/17/graalvm/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_17-graalvm`
* [`java21`](/java/21/)
  * [`java21-temurin`](/java/21/temurin/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_21-temurin`
  * [`java21-semeru`](/java/21/semeru/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_21-semeru`
  * [`java21-graalvm`](/java/21/graalvm/Dockerfile)
    * `ghcr.io/pizzabytellc/images:java_21-graalvm`

### [Installation Images](/installers)

These images are used by install scripts for different Eggs within Pterodactyl, not for actually running a game server. These images are only designed to reduce installation time and network usage by pre-installing common installation dependencies such as `curl` and `wget`.

* [`alpine`](/installers/alpine)
  * `ghcr.io/pizzabytellc/installers:alpine`
* [`debian`](/installers/debian)
  * `ghcr.io/pizzabytellc/installers:debian`
* [`ubuntu`](/installers/ubuntu)
  * `ghcr.io/pizzabytellc/installers:ubuntu`
