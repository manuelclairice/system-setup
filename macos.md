1. Click on the magnifying glass at the very top right of your screen to open the Spotlight search, enter "terminal.app" and hit return:<br><br>
   <img src="./macos-1-start-terminal.png">
   <br>This will launch the macOS terminal.<br><br>
2. Copy the following text, paste it in the terminal and hit return.<br><br>
   ```bash
   xcode-select --install
   ```
   It will pop up a prompt similar to the screenshot below. Click "Install":<br><br>
   <img src="./macos-1.1-xcode-command-line-tools.png"><br><br>
   This will install the Xcode Command Line Tools, tools that enable installation of other software.<br><br>
3. Copy the following text, paste it in the terminal and hit return.<br><br>
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
   This will install Homebrew, a package manager which will allow us to install and uninstall programs from the terminal.<br><br>
4. Hit return when the installer asks you to:<br><br>
   <img src="./macos-2-hit-return.png"><br><br>
   Also enter your Mac password when the installer asks you to.<br><br>
   ‼️ Note: while typing your password, you will not see the letters being entered. This is normal:<br><br>
   <img src="./macos-3-enter-password.png"><br><br>
5. The installer will take a bit of time and then show a message that "Installation successful!", signaling that it is done:<br><br>
   <img src="./macos-4-installation-successful.png"><br><br>
   Read the messages underneath the "Installation successful!" message and look for a heading that says "Next steps". If there is a bullet point with the text "Add Homebrew to your PATH...", then there are be some additional commands that you need to copy and run (copy each line, paste it in the terminal and hit return):<br><br>
   <img src="./macos-4.1-homebrew-next-steps.png"><br><br>
6. Copy the following text, paste it in the terminal and hit return.<br><br>
   ```bash
   brew install git node yarn
   ```
   This uses Homebrew to install Git, Node.js and Yarn.<br><br>
7. Copy each line in the following text, paste it in the terminal and hit return.<br><br>
   ```bash
   brew tap microsoft/git
   brew install --cask visual-studio-code postman git-credential-manager-core
   ```
   This uses Homebrew Cask to install Visual Studio Code, Postman and Git Credential Manager Core.<br><br>
   If you don't have Zoom installed yet, run this to install it:<br>
   ```bash
   brew install --cask zoom
   ```
   If you don't have Slack installed yet, run this to install it:<br>
   ```bash
   brew install --cask slack
   ```
8. Copy each line in the following text, paste it in the terminal and hit return.<br><br>

   ```bash
   code --install-extension Cardinal90.multi-cursor-case-preserve
   code --install-extension dbaeumer.vscode-eslint
   code --install-extension dozerg.tsimportsorter
   code --install-extension esbenp.prettier-vscode
   code --install-extension frigus02.vscode-sql-tagged-template-literals
   code --install-extension styled-components.vscode-styled-components
   code --install-extension kumar-harsh.graphql-for-vscode
   code --install-extension meganrogge.template-string-converter
   code --install-extension stylelint.vscode-stylelint
   code --install-extension sysoev.vscode-open-in-github
   code --install-extension wix.glean
   ```

   This installs some VS Code extensions we will need.<br><br>

9. We recommend installing and using Chrome so that you have the same DevTools as others.<br><br>
   If you don't have Chrome installed yet, you can install it with Homebrew. To do this, copy the following text, paste it in the terminal and hit return.<br><br>
   ```bash
   brew install --cask google-chrome
   ```
   This uses Homebrew to install Chrome.<br><br>
10. Install the following Chrome Extensions:
    - [React Developer tools Chrome Extension](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)
    - [Refined GitHub Chrome Extension](https://chrome.google.com/webstore/detail/refined-github/hlepfoohegkhhmjieoechaddaejaokhf?hl=en)
    - [Web Vitals Chrome Extension](https://chrome.google.com/webstore/detail/web-vitals/ahfhijdlegdabablpippeagghigmibma?hl=en))
11. Copy the following text, paste it in the terminal and hit return.<br><br>

    ```bash
    yarn create react-app --help
    ```

    This step will prepare a program that we will use in the course. This will take a while and then respond with a message that some modules have been installed, similar to this:<br><br>
    <img src="./general-1-cra-installed.png"><br><br>

12. Copy the following text, paste it in the terminal and hit return.<br><br>
    ```bash
    yarn global add @upleveled/preflight
    ```
    This will prepare a program that we will use in the course.<br><br>
13. Next we will configure VS Code.<br><br>
    Open VS Code and then press the keys <kbd>cmd</kbd>-<kbd>shift</kbd>-<kbd>P</kbd>. Type in "Settings" and select the item that says `Preferences: Open Settings (JSON)`:<br><br>
    <img src="./general-2-vscode-settings.png"><br><br>
    Once the settings file is open, we will want to add the settings below.<br><br>
    First of all, identify whether your settings file is empty or not. This is what an empty file looks like:<br><br>
    <img src="./general-3-vscode-settings-empty.png"><br><br>
    If your file is **not empty** (if there is more text within the curly brackets), then **we will need to do something extra** - add a comma on the second to last line:<br><br>
    <img src="./general-4-vscode-settings-comma.png"><br><br>
    Now in both cases you will want to paste the following settings **before the closing curly bracket (before the `}`)**:<br><br>
    ```json5
    "editor.wordWrap": "on",
    "editor.minimap.enabled": false,
    "editor.formatOnSave": true,
    "tsImportSorter.configuration.groupRules": ["^node:", {}, "^[.]"],
    "tsImportSorter.configuration.keepUnused": [".*"],
    "tsImportSorter.configuration.emptyLinesBetweenGroups": 0,
    "tsImportSorter.configuration.wrappingStyle": "prettier",
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "[html]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[javascript]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[javascriptreact]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[typescript]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[typescriptreact]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[json]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[jsonc]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "files.autoSave": "onFocusChange",
    "explorer.openEditors.visible": 0,
    "editor.tabSize": 2,
    "files.trimTrailingWhitespace": true,
    "files.trimFinalNewlines": true,
    "[markdown]": {
      "files.trimTrailingWhitespace": false
    },
    "workbench.editor.tabSizing": "shrink",
    "workbench.editor.closeEmptyGroups": false,
    "prettier.singleQuote": true,
    "prettier.trailingComma": "all",
    "eslint.runtime": "node",
    ```
    If you had any previous settings beforehand, you may notice that some text above will be underlined by a squiggly yellow line. This is a warning because we pasted some duplicate properties from the code above.<br><br>
    If you have any of these warnings, we should fix them. For each one of these lines with the warnings on them, delete the full line, including the comma at the end. We usually like to select from the start of the first `"` to just before the next `"` on the next line:<br><br>
    <img src="./general-5-vscode-settings-fix-warnings.png"><br><br>
14. <a name="postgresql"></a>We will now install PostgreSQL. Copy the following text, paste it in the terminal and hit return.

    ```bash
    brew install postgresql
    ```

    This uses Homebrew to install PostgreSQL and create just a single user with your username and all role permissions. There will be no `postgres` user set up.<br><br>
    Now let's set an environment variable to tell PostgreSQL where to put the data:

    ```bash
    [[ -d /opt/homebrew/var/postgres ]] && PGDATA_TMP=/opt/homebrew/var/postgres || PGDATA_TMP=/usr/local/var/postgres
    echo "export PGDATA=$PGDATA_TMP" >> ~/`[[ $SHELL == *"zsh" ]] && echo '.zshrc' || echo '.bash_profile'`
    source ~/`[[ $SHELL == *"zsh" ]] && echo '.zshrc' || echo '.bash_profile'`
    ```

    We can now test whether PostgreSQL has been correctly installed by starting the database. To do this, we can run the following command:

    ```bash
    postgres
    ```

    If it worked, it should print out some lines with some messages and end with the rectangular cursor on the left side of the screen:

    <img src="./macos-5-postgres.png"><br><br>

    The messages may be different than the messages in the image above, and may not mention that PostgreSQL is ready to accept connections:

    <img src="./windows-5-postgres.jpg"><br><br>

    You will need to run this every time you want to use your database.<br><br>
    When you want to stop PostgreSQL again, just stop it like any other command line program using the shortcut <kbd>control</kbd>-<kbd>C</kbd>.

    Now we will connect to PostgreSQL using a tool called `psql` and add a new table, to make sure everything is working with the connection.

    Open a new tab in the terminal using <kbd>command</kbd>-<kbd>T</kbd> and run the following command:

    ```bash
    psql postgres
    ```

    It should look like this:<br><br>

    <img src="./macos-5.1-psql.png"><br><br>

    If your screen looks like the above screenshot, type in or copy and paste the following query (this is a language called SQL):

    ```sql
    CREATE TABLE users(
      id serial PRIMARY KEY,
      first_name VARCHAR (100) NOT NULL,
      last_name VARCHAR (100) NOT NULL
    );
    ```

    It should print `CREATE TABLE` on the line after running the query. Your screen should look like this:<br><br>

    <img src="./macos-5.2-psql.png"><br><br>

    Now let's check that the table has been created. Run this query:

    ```
    \dt
    ```

    This will show the tables that you have, including the newly-created `users` table. Your screen should look like this:<br><br>

    <img src="./macos-5.3-psql.png"><br><br>

    Finally, let's delete the table again to clean up. Run this query:

    ```sql
    DROP TABLE users;
    ```

    It should print `DROP TABLE` on the line after running the query. Your screen should look like this:<br><br>

    <img src="./macos-5.4-psql.png"><br><br>

    Great, PostgreSQL is set up! 🚀 Now you can exit from `psql` again by writing `exit` and hitting return:

    ```
    exit
    ```

    It should exit and send you back to the command line. Your screen should look similar to this (the last line will not be exactly the same):<br><br>

    <img src="./macos-5.5-psql.png"><br><br>

    Now close the new terminal tab with <kbd>command</kbd>-<kbd>W</kbd>, and stop PostgreSQL again using <kbd>control</kbd>-<kbd>C</kbd>. PostgreSQL should shut down - your screen should look similar to this (the last line will not be exactly the same):<br><br>

    <img src="./macos-5.6-psql.png"><br><br>

15. <a name="docker"></a>We will now install Docker. Copy the following text, paste it in the terminal and hit return.

    ```bash
    brew install --cask docker
    open /Applications/Docker.app
    ```

    This uses Homebrew Cask to install Docker for Mac and starts it for the first time to set it up. Wait for a message at the top of the window to indicate that everything is finished being set up:<br><br>
    <img src="./macos-6-docker.png"><br><br>

16. Test if Docker is installed by running the following command on the command line:

    ```bash
    docker run hello-world
    ```

    It should print out a welcome message like this:<br><br>
    <img src="macos-6-docker-hello-world.png"><br><br>

17. <a name="expo-react-native"></a>We will now install Expo CLI for React Native.

    Copy the following text, paste it in the terminal and hit return.

    ```bash
    npm install -g expo-cli
    ```

    On your phone, go to the app store and install Expo on your phone ([Android](https://play.google.com/store/apps/details?id=host.exp.exponent&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/expo-go/id982107779)). Create an account and log in.

18. Install the Android Studio Emulator for Expo by following this guide: https://docs.expo.io/workflow/android-studio-emulator/

    If this guide doesn't work and your computer has an M1 (Apple Silicon) chip, try this: https://github.com/expo/expo/issues/13313#issue-923722853

19. To verify that Expo is working with Android Studio, first start Android Studio, click on "Configure" and select AVD Manager. Click on the green play button next to one of the devices.

    Then copy and run each of these lines separately in the terminal:

    ```bash
    cd ~
    mkdir projects
    cd projects
    npx create-react-native-app --template blank expo-test
    cd expo-test
    yarn
    yarn start
    ```

    This should run an Expo demo application, which will show you the Expo Developer Tools.

    In the left panel, select "Run on Android device/emulator". This will start a process that should open up an Android emulator - a simulator of an Android mobile device. The process may take several minutes. If the Android device says "System UI isn't responding", then click on "Wait".

    Once it is loaded, it should show the words "Universal React with Expo".

    If you're having troubles, the process should look something like shown in [Setup React Native with Android Studio (Expo) - Emulator & Physical device setup | YouTube](https://youtu.be/gVGuNxkh8ig?t=808)

20. If you don't have one yet, create a Google account [here](https://accounts.google.com/signup?hl=en). Send the email address associated with this account to Karl (if you haven't already).
21. If you don't have one yet, create a GitHub account [here](https://github.com/join). Make sure to set a name.

    If you already have a GitHub account and you haven't set a name on GitHub yet, go to the [GitHub Profile Settings](https://github.com/settings/profile) and add a name:<br><br>
    <img src="./general-6-github-profile-settings.png"><br><br>
    We will use this name in the next step.<br><br>

22. For this step, we'll need to **edit some of the information in the commands** by adding our own information.<br><br>
    First of all, we will set our name, which will be the same name as on our GitHub profile:<br><br>
    <img src="./general-7-github-name.png"><br><br>
    Copy your name from your profile, **add it in quotes** in the command (replace `Mona Lisa Octocat`) and run the command:<br><br>
    ```bash
    git config --global user.name "Mona Lisa Octocat"
    ```
    You can test whether the name was set correctly with the next command (if it worked, it will print the name on the next line):<br><br>
    ```bash
    git config --global user.name
    ```
    <br>For running the next command, **add your email in quotes**:<br><br>
    ```bash
    git config --global user.email "monalisaoctocat@example.com"
    ```
    You can test whether the email was set correctly with with the next command (if it worked, it will print the email on the next line):<br><br>
    ```bash
    git config --global user.email
    ```
    This prepares `git` so that your work is attributed correctly to you.<br><br>

<!-- 23. Copy the following text, paste it in the terminal and hit return.<br><br>
    ```bash
    git config --global credential.helper osxkeychain
    ```
    This step will save your GitHub password so that you don't need to enter it every time.<br><br> -->

23. Copy the following text, paste it in the terminal and hit return.<br><br>
    ```bash
    git config --global init.defaultBranch main
    ```
    This step will change the default Git branch from `master` to `main` (see https://github.com/github/renaming).<br><br>
24. Go back to GitHub, and go to your profile page by clicking on your avatar at the top right and selecting **Your profile**<br><br>
    <img src="./general-8-github-your-profile.png"><br><br>
    Copy the `github.com/...` URL in the address bar of your browser, for use in the next step.
25. Click on Applications in the dock and start Slack. Log in to the UpLeveled Slack. Send your GitHub profile URL to Karl.
26. Click on the apple icon in the menu bar at the top left of your screen and select "About This Mac". Select "System Report...". Copy the "Hardware Overview" information in the right panel and send to Karl. Select "Software" in the left panel, copy the "System Software Overview" information and send to Karl.
27. On your phone, go to the app store and install Slack on your phone. Log in to the UpLeveled Slack.

## Optional Software

1. If you would like to check the spelling of all code you write in VS Code, try out [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker). You can install on the command line with this command:

   ```bash
   code --install-extension streetsidesoftware.code-spell-checker
   ```

2. If you want to easily capture screenshots and draw and write on them, try Flameshot:

   ```bash
   brew install --cask flameshot
   ```

3. If you need to record video of your screen with sound (with export to mp4 and gif), you may want to try out Kap:

   ```bash
   brew install --cask kap
   ```

4. If you would like to keep a history of what you have copied to your clipboard, you can try out Yippy:

   ```bash
   brew install --cask yippy
   ```

5. To simultaneously test your web design in multiple mobile viewports, try Responsively App:

   ```bash
   brew install --cask responsively
   ```

6. To remove secrets, large files or other undesirable files from your Git repository, try BFG Repo-Cleaner:

   ```bash
   brew install bfg
   ```

7. If you're running out of space on your computer, you can use Disk Inventory X to analyze your hard drive and show a chart of which items are taking up how much space:

   ```bash
   brew install --cask disk-inventory-x
   ```

8. To do natural language calculations and conversions, try [Numi](https://numi.app/):

   ```bash
   brew install --cask numi
   ```
