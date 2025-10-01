# Paysecure API SDK

## Installation for java 21

### 1. Install SDK from the root folder
```bash
mvn install:install-file -Dfile=paysecure-sdk-1.0.jar -DgroupId=com.paysecure.sdk -DartifactId=paysecure-sdk -Dversion=1.0 -Dpackaging=jar
```

### 2. Add Dependency
Add to your project's `pom.xml`:
```xml
<dependency>
    <groupId>com.paysecure.sdk</groupId>
    <artifactId>paysecure-sdk</artifactId>
    <version>1.0</version>
</dependency>
```

### 3. Configuration
Set environment variables:
```bash
export PAYSECURE_API_BASE_URL=https://api.paysecure.com
export PAYSECURE_API_KEY=your-api-key-here
export PAYSECURE_DEBUG=true/false
