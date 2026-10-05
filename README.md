# Rewloy Maven

**https://maven.rewloy.com**

**Türkçe.** Rewloy istemci kütüphanelerinin Maven deposu. Burada yalnız
yayımlanmış paketler durur; kaynak kodu
[Rewloy/rewloy-kotlin](https://github.com/Rewloy/rewloy-kotlin) deposundadır.
Dosyalar elle eklenmez: rewloy-kotlin'de bir `v*` etiketi, Release iş akışıyla
yeni sürümü buraya yazar. Yayımlanmış bir sürüm sonradan değişmez. Geliştirici
belgeleri: https://rewloy.com/gelistiriciler

**English.** The Maven repository of the Rewloy client libraries. It holds
published packages only; the source is in
[Rewloy/rewloy-kotlin](https://github.com/Rewloy/rewloy-kotlin). Nothing is
added by hand: a `v*` tag in rewloy-kotlin makes its Release workflow add the
new version here, and a published version never changes afterwards. Developer
docs (Turkish): https://rewloy.com/gelistiriciler

| Paket / Artifact | |
|---|---|
| `com.rewloy:rewloy` | Kütüphane / the library (Kotlin, Java, Android 5.0+) |
| `com.rewloy:rewloy-okhttp` | İsteğe bağlı OkHttp taşıyıcısı / optional OkHttp transport |
| `com.rewloy:rewloy-coroutines` | İsteğe bağlı `suspend` ve `Flow` / optional `suspend` and `Flow` |

Sürümler / Versions: [CHANGELOG](https://github.com/Rewloy/rewloy-kotlin/blob/main/CHANGELOG.md).

## Gradle (Kotlin DSL)

```kotlin
// build.gradle.kts. Android Studio: the repositories go in settings.gradle.kts,
// inside dependencyResolutionManagement { repositories { … } }.
repositories {
    mavenCentral()
    maven("https://maven.rewloy.com") {
        content { includeGroup("com.rewloy") }   // only com.rewloy is looked up here
    }
}

dependencies {
    implementation("com.rewloy:rewloy:0.2.3")
    implementation("com.rewloy:rewloy-okhttp:0.2.3")      // optional
    implementation("com.rewloy:rewloy-coroutines:0.2.3")  // optional
}
```

## Gradle (Groovy)

```groovy
repositories {
    mavenCentral()
    maven {
        url = 'https://maven.rewloy.com'
        content { includeGroup 'com.rewloy' }
    }
}

dependencies {
    implementation 'com.rewloy:rewloy:0.2.3'
}
```

## Maven

```xml
<repositories>
  <repository>
    <id>rewloy</id>
    <url>https://maven.rewloy.com</url>
    <snapshots><enabled>false</enabled></snapshots>
  </repository>
</repositories>

<dependencies>
  <dependency>
    <groupId>com.rewloy</groupId>
    <artifactId>rewloy</artifactId>
    <version>0.2.3</version>
  </dependency>
</dependencies>
```

Her paketin yanında kaynak (`-sources.jar`), javadoc jar'ı, POM, Gradle modül
dosyası ve sağlama toplamları (MD5, SHA-1, SHA-256, SHA-512) vardır.

Every package comes with a sources jar, a javadoc jar, its POM, Gradle module
metadata and checksums (MD5, SHA-1, SHA-256, SHA-512).
