plugins {
    id 'java-library'
    id 'maven-publish'
    id 'application'
}

application {
    mainClass = 'com.pgm4.dev.test.App'
}

repositories {
    mavenLocal()
    maven {
        url = uri('https://repo.maven.apache.org/maven2/')
    }
}

dependencies {
    testImplementation libs.junit.junit
}

group = 'com.pgm4.dev'
version = '0.0.1-SNAPSHOT'
description = 'pgm4'
java.sourceCompatibility = JavaVersion.VERSION_1_8

publishing {
    publications {
        maven(MavenPublication) {
            from(components.java)
        }
    }
}

tasks.withType(JavaCompile) {
    options.encoding = 'UTF-8'
}

tasks.withType(Javadoc) {
    options.encoding = 'UTF-8'
}
