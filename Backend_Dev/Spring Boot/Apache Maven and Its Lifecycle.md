
---
**Apache Maven** is a **build automation and dependency management tool** primarily used for **Java projects**.

It helps developers:

- Manage **project dependencies** (libraries, frameworks).
    
- **Build** and **package** applications.
    
- Maintain a consistent **project structure**.
    
- Handle **testing**, **deployment**, and **documentation** automatically.
    

 ⚙️ Key Features

- **Dependency Management** → handles all external libraries via `pom.xml`.
    
- **Build Lifecycle** → automates compile, test, package, deploy steps.
    
- **Convention over Configuration** → follows standard directory structure.
    
- **Plugins** → extend Maven’s functionality (compiler, surefire, jar, etc.).


```
my-app/
 ├── src/
 │   ├── main/
 │   │    ├── java/          # source code
 │   │    └── resources/     # config files
 │   └── test/
 │        ├── java/          # test classes
 │        └── resources/
 ├── target/                 # compiled output
 └── pom.xml                 # Maven configuration file
```

## Maven Lifecycle Overview

Maven has **three main lifecycles**, each with predefined **phases** that run in order.

1️⃣ **Clean Lifecycle**

Cleans the project by removing files generated from previous builds.

|Phase|Description|
|---|---|
|`pre-clean`|Tasks before cleaning.|
|`clean`|Deletes the `target/` directory.|
|`post-clean`|Tasks after cleaning.|

```bash
mvn clean
```

2️⃣ **Default (Build) Lifecycle**

Handles the **complete build process** — from compile to deploy.

| Phase      | Description                                                        |
| ---------- | ------------------------------------------------------------------ |
| `validate` | Validate the project is correct and complete.                      |
| `compile`  | Compile source code (`src/main/java`).                             |
| `test`     | Run unit tests (`src/test/java`).                                  |
| `package`  | Package compiled code into JAR/WAR.                                |
| `verify`   | Run checks on integration tests/results.                           |
| `install`  | Install built artifact into local Maven repo (`~/.m2/repository`). |
| `deploy`   | Deploy artifact to remote repository (for sharing).                |

```bash
mvn compile
mvn test
mvn package
mvn install
mvn deploy
```

3️⃣ **Site Lifecycle**

Generates documentation or project reports.

| Phase         | Description                          |
| ------------- | ------------------------------------ |
| `pre-site`    | Prepare site generation.             |
| `site`        | Generate project site documentation. |
| `post-site`   | Finalize site creation.              |
| `site-deploy` | Publish the generated site.          |

```bash
mvn site
```

## 🔄 Full Lifecycle Example

When you run:

```
mvn clean install
```

Maven executes:

```
clean → validate → compile → test → package → verify → install
```

