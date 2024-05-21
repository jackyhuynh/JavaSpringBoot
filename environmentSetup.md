Here is the cleaned-up and formatted version of your instructions:

# JAVA VIRTUAL MACHINE TROUBLESHOOT

## Code is not Compiling:

- **Issue**: After cloning the project from the upstream repository, the application doesn't compile.
- **Possible Causes**:
  - Incompatible Java version
  - Incompatible Gradle version
  - Missing dependencies
  - Incorrect project structure

### Precondition:

- Operating System: macOS Sonoma 14.5
- Hardware: MacBook Pro M3
- Chip: Apple M3 Pro

### Steps to Fix:

1. **Check Gradle JDK Version**:
    - Open IntelliJ IDEA.
    - Go to **Settings** (or press `Command + ,`).
    - Search for "Gradle" in the search bar.
    - Ensure the correct JDK version is selected (you may need to download the appropriate version by clicking `Download JDK`).
    - **Note**: Often, you need to match the JVM version with the one used by the developer who created the project.

2. **Check Java Compiler Version**:
    - Open IntelliJ IDEA.
    - Go to **Settings** (or press `Command + ,`).
    - Search for "Java Compiler" in the search bar.
    - Ensure the Java Compiler is set to the correct version (e.g., Java 21).
    - You may need to download the appropriate Java version. This can be done through Homebrew to ensure dependency consistency.

3. **Check JAVA_HOME Environment Variable**:
    - If issues still occur after the above changes, the problem might be with the `JAVA_HOME` environment variable.
    - Troubleshoot by running the following commands in Terminal:

    ```bash
    echo $JAVA_HOME # Check if a path is displayed. If so, it might need to be removed to ensure IntelliJ uses the JVM set within it.
    cd ~ # Navigate to the home directory
    ls -al # Check if .zshrc or other shell configuration files exist
    vim .zshrc # Edit the .zshrc file
    ```

    - In the `.zshrc` file (or other relevant shell configuration files), remove any lines related to `JAVA_HOME` or Java paths.
    - Also, remove paths related to Homebrew Java (if necessary).

4. **Check for Missing Dependencies**:
    - Ensure that all project dependencies are correctly imported.
    - Open the **Terminal** in IntelliJ IDEA.
    - Run `./gradlew clean build` to clean and rebuild the project.

5. **Check Project Structure**:
    - Make sure the project structure is correctly configured.
    - Go to **File > Project Structure**.
    - Verify that the SDK and language level are correctly set.

6. **Check for IntelliJ IDEA Caches**:
    - Sometimes, invalid caches can cause issues.
    - Go to **File > Invalidate Caches / Restart**.
    - Choose "Invalidate and Restart".

7. **Check for Conflicting Plugins**:
    - Ensure that there are no conflicting plugins that might be causing issues.
    - Go to **File > Settings > Plugins**.
    - Disable any unnecessary or conflicting plugins and restart IntelliJ IDEA.

8. **Update IntelliJ IDEA and Plugins**:
    - Ensure that IntelliJ IDEA and all plugins are up to date.
    - Go to **Help > Check for Updates** and install any available updates.

## Result:

By following these steps, you can address a wide range of potential issues that may prevent your project from compiling successfully.`