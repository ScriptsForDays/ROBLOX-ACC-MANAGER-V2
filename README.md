# Roblox Account Manager

Application that allows you to add multiple accounts into one application allowing you to easily play on alt accounts without having to change accounts.

Useful for games that require grinding off other players, or storage accounts that hold in game items or currency, or just to have multiple accounts that you can easily find and use.

Multiple Roblox Instances is built into the account manager but **must be manually enabled** in settings.

# WARNING

If someone asks you to generate an "rbx-player link", **DO NOT** do it, they can use these to join any game using your account, or even launch roblox studio with one of your games. They can do many things in game such as spend your robux or even do things that can get your account terminated. **USE THESE FEATURES AT YOUR OWN RISK**

# Installation

1. Download and extract all files from this repository
2. **Keep all files in the same folder** - The application requires all files to be in the same directory
3. Run `Roblox Account Manager.exe`
4. On first launch, you will be prompted to choose your encryption method:
   - **Default Encryption** (Windows DPAPI) - Recommended for single computer use
   - **Password Encryption** - Recommended if you want to backup your accounts or use on multiple computers
5. Add your accounts using the "Open Browser" button

## Requirements

- Windows 10 or later
- [.NET Framework 4.7.2 or later](https://dotnet.microsoft.com/download/dotnet-framework)
- Roblox installed on your system
- [Visual C++ Redistributable (x86)](https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist) - Required for CefSharp browser components

If the application isn't starting or not working, make sure to install the [Latest .NET Framework](https://dotnet.microsoft.com/download/dotnet-framework). Still having issues? Download and install [vcredist](https://aka.ms/vs/16/release/vc_redist.x86.exe)

## Important Notes

- **Do not delete the `x64` and `x86` folders** - These contain required CefSharp dependencies
- **Do not delete `handle.bin`** - Required for multi-instance functionality
- **Account persistence** - Your logged-in accounts are automatically saved to `AccountData.json` (created automatically when you add your first account)
- **You don't need to sign in every time** - Once you add an account, it stays logged in until the cookie expires
- First run will create configuration files automatically (`RAMSettings.ini`, `RAMTheme.ini`)
- All user data is stored locally and encrypted
- **DO NOT SHARE YOUR `AccountData.json` FILE** - It contains your account cookies and encrypted data

# Frequently Asked Questions

## **Q:** Why is this program detected as a virus?

**A:** Open source programs such as this program are commonly detected as viruses because actual malware may be using the same libraries as this one. For example, account manager may be detected as a RAT because of the Account Control feature, this feature uses websockets to connect to clients which is the same way actual malware may use to connect maliciously to someone else's computer. The application uses legitimate Windows APIs and libraries for account management and multi-instance functionality.

## **Q:** How do I enable multi-roblox?

**A:** Open the settings menu by clicking the gear/cog icon in the top right, in the `General` tab, you will see a checkbox for `Multi Roblox`, make sure you have Roblox closed, then check the checkbox. **Note:** Multi-instance functionality requires `handle.bin` to be present in the application folder.

## **Q:** Why was multi-roblox disabled by default?

**A:** A byfron developer has stated that using multiple clients may be considered as malicious behavior, so multi-roblox is disabled by default and users must enable the option manually at their own risk.

## **Q:** Why am I getting CefSharp.Core.Runtime.dll/Object reference not set errors, how do I fix it?

**A:** Download the x86 version from [Microsoft Visual C++ Redistributable](https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist). On an older OS? Try downloading [older versions of vcredist](https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170#visual-studio-2013-vc-120) by scrolling down on or clicking the link. If that doesn't work, download the latest .NET Framework from [dotnet.microsoft.com](https://dotnet.microsoft.com/download/dotnet-framework).

## **Q:** Why do my accounts have yellow/red dots on them?

**A:** The yellow-red dots that appear on an account means that account hasn't been used in over 20 days, as that day counter goes up, the dot appears more red. You can get rid of this dot by joining a game or enabling developer mode and clicking "Get Authentication Ticket" when you right click an account (works with multiple).

## **Q:** How do I backup my accounts file?

**A:** Your `AccountData.json` file is encrypted. If you chose password encryption, you can backup the file and restore it on another computer. If you chose default encryption (Windows DPAPI), the file is tied to your Windows user account and cannot be moved to another computer. **DO NOT share your AccountData.json file with anyone.**

## **Q:** How do I prevent Windows Defender from deleting alt manager files?

**A:** Add an exclusion for the Roblox Account Manager folder. You can do this by going to Windows Security > Virus & threat protection > Manage settings > Exclusions > Add or remove exclusions, then add the folder containing the application.

## **Q:** Can I join VIP servers using alt manager?

**A:** Yes you can, just make sure the place id is the same as the game you're trying to join, then paste the whole VIP server link into the Job ID box and press Join Server.

## **Q:** My anti virus detects this program as a virus. Should I not use it?

**A:** This program is in no way malicious. Some anti-virus programs may detect Account Manager as malicious because of features like multi-instance support, process manipulation, and cookie handling - all of which are legitimate features for account management. These are false positives.

## **Q:** Can you use this on Mac?

**A:** No, unfortunately we do not have compatibility with Mac OSX devices at this moment. This may change in the future.

## **Q:** I can't launch multiple accounts repeatedly.

**A:** This is due to Roblox's rate limiting. Wait a few seconds between launches.

## **Q:** Adding an account doesn't work

**A:** Make sure you have a stable internet connection and that CefSharp dependencies are properly installed. Try restarting the program if issues persist.

## **Q:** Can you get banned for using this?

**A:** No, you cannot get banned for using this as this does not break Roblox T.O.S although some games may disallow you from having alt accounts so please do your research if you are unsure.

## **Q:** My AccountData file gets corrupted often

**A:** This is due to ProtectedData failing sometimes. You can disable encryption by creating a file called `NoEncryption.IUnderstandTheRisks.iautamor` in the application folder. **Do this at your own risk, nobody except yourself is responsible for your accounts!**

## **Q:** Multi-instance doesn't work after Roblox update

**A:** Make sure `handle.bin` is present in the application folder. If it still doesn't work, ensure Roblox is completely closed (check Task Manager for any Roblox processes) before enabling multi-instance, then restart the application.

# Features

| Feature | Description | How to |
| :--- | :---: | ---: |
| Account Encryption | All your account data is locally encrypted using your computer as the **password/key** meaning if someone else gets a hold of your account data, they will **NOT** be able to decrypt it unless you decrypted it yourself and shared it | Choose encryption method on first launch |
| Password Encryption | Use a password to encrypt your data | Choose "Password Encryption" on first launch - recommended if you want to backup your accounts |
| Multi Roblox | RAM comes with a built-in multi Roblox allowing multiple Roblox clients to be open at once | Open settings (gear icon), go to `General` tab, check `Multi Roblox`. **Make sure Roblox is closed first!** |
| Server List | See a game's servers, including the servers' data such as player count and server ping | Click `Server List` on the right side of the main window |
| Join Small Servers | Easily join small servers in games that use lobby starter places to teleport you to another game | Insert the actual game's PlaceId into the text box next to `Refresh` in the `Server List`, click `Refresh`, then right click a server and click `Join Game` |
| Account Utilities | Easily change your account password, email, follow privacy, etc | Click `Account Utilities` in the main window **(Requires a valid account to be selected in the main window)** |
| Account Sorting | Sort your accounts easily | Simply drag and drop an account on the list |
| Account Grouping | Sort your accounts by groups, you can also drag and drop accounts into other groups | Right click an account, hover over `Groups`, then click `Move account to` |
| Group Sorting | Sort groups from top to bottom by assigning numbers to them | When creating a group, you can put a number from 0-999 (ex. `1Main`, `007 Bank`, `67 Dead`, ...), sorted from smallest to largest, the numbers will be hidden afterwards |
| Games List | Browse through thousands of games you normally wouldn't see on the front page | Click `Server List`, then `Games` |
| Favorite Games | Add your favorite games to a list you can easily navigate to | Click `Server List`, then `Favorites` |
| Recent Games | Saves your recently played games into the `PlaceId` text box | After joining a game, that game will be added to the recent games list, which you can then quickly load up by hovering over the clock icon above the `PlaceId` text box or by typing the game's name into the `PlaceId` text box in the main window |
| Open Browser | Open a browser window using the selected account, allowing you to access various settings | Click `Open Browser` in the main window while having an account selected |
| Join VIP Servers | Join VIP servers easily | Simply place your entire VIP server link into the `PlaceId` text box and RAM will handle the rest |
| Shuffle JobId | Selects a random JobId for every account everytime you press "Join Server" unless you have a JobId set | Click the shuffle icon to toggle JobId Shuffler |
| Save PlaceId & JobId | Save specific `PlaceId`s and/or `JobId`s to specific accounts | Once you enter your desired PlaceId and/or VIP links, click the `Save` icon next to the `JobId` text box |
| Player Finder | Find a player even if their follows are off as long as you know what game they are in | In the `Server List` window, put a player's username into the `Username` text box, then click search. **This may take a while to load and may be patched in the near future** |
| Universe Viewer | View a game's universe | Open `Utilities`, then click `Universe` |
| Outfit Viewer | View other player's outfits and even wear their outfits | Open `Utilities`, then click `Outfits` |
| Sort Account by Usage Date | View the last time you used an account | Make sure to enable headers in the Theme Editor, right click the header and enable `Last Used`, then right click an account, hover `Groups`, and press `Toggle`. You can now click on `Last Used` in the header to sort the accounts. |
| Close Roblox Beta | Detects if the Roblox Beta Home Menu is open and terminates the process if so | Open `Utilities`, then click `Watcher` to modify settings |
| Prevent Duplicate Instances | Automatically shuts down old instances when you launch an account | Account Manager automatically assigns a number called `BrowserTrackerID` to each account allowing it to know if there is an active instance of that specific account running, then proceeds to close it preventing instances of the same account opening more than once |
| Save Passwords | Upon logging into an account, RAM will automatically save that accounts password which can then be copied by right clicking the account, then selecting `Copy Password` | This can be disabled by clicking the settings button (gear cog in top-right corner), then unchecking `Save Passwords` |
| Themes | Customize RAM to your liking | Click `Edit Theme` in the main window |
| Developer Mode | Enable hidden features not available to normal users for safety reasons | Click the settings button (gear cog in top-right corner), click `Developer`, then check the `Enable Developer Mode` box |
| Import Cookies | Import accounts using their .ROBLOSECURITY cookies | You can drag and drop one or multiple cookies directly into the program, or you can enable developer mode and use the `Import` window |
| FPS Unlocker | Unlocks the Roblox client's FPS using Roblox's ClientAppSettings.json | Settings can be found by clicking the settings cog, then miscellaneous |
| Bulk User Importing | Easily import your accounts by their username & password combos, or by cookies | Click the arrow on the right side of the `Add Account` button, then select user:pass/cookies |
| Automatic Connection Loss Detection | Closes instances that are not connected to a server for a certain amount of time | To enable this, go to `Utilities`->`Watcher`, and make sure `Enable Roblox Watcher` is checked as well as `Exit if No Connection to Server` |
| Automatic Cookie Refresh | Your accounts never become invalidated sitting in the account manager over long periods of time | As long you actively use account manager, your accounts will regularly get new cookies preventing them from being logged out, this does sign you out of other sessions though |
| Join Group | Easily join groups with multiple accounts | Click the arrow on the right side of the `Open Browser` button, then click `Join Group` |
| Quick Log In | Easily log in to an account on a different computer using Roblox's Quick Log In feature | Right click an account, then select `Quick Log In` |
| StreamProof | Hides the application from screen recording software (OBS, Streamlabs, etc.) to protect your privacy | Open settings (gear icon), go to `Miscellaneous` tab, check `StreamProof` |
| Anti-Screenshot | Prevents screenshots and screen captures of the application windows | Open settings (gear icon), go to `Miscellaneous` tab, check `Anti-Screenshot` |
| Support Original Owner | Support the original creator of Roblox Account Manager (ic3w0lf22) | Open settings (gear icon), go to `Support` tab, click `Support the original owner` |

# Troubleshooting

- **Multi-instance doesn't work**: Ensure `handle.bin` is present in the application folder and that Roblox is completely closed before enabling multi-instance
- **Application won't start**: Install [.NET Framework 4.7.2+](https://dotnet.microsoft.com/download/dotnet-framework) and [Visual C++ Redistributable (x86)](https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist)
- **CefSharp errors**: Download and install the x86 version of Visual C++ Redistributable
- **Authentication errors**: Re-add accounts if you get authentication errors (cookies may have expired)
- **Accounts not saving**: Make sure the application folder has write permissions and that `AccountData.json` is not read-only

# License

This project is based on the original [Roblox Account Manager](https://github.com/ic3w0lf22/Roblox-Account-Manager) by ic3w0lf22, which is licensed under GPL-3.0.

# Disclaimer

This software is provided as-is. Use at your own risk. The developers are not responsible for any account bans, data loss, or other issues that may arise from using this software. Always keep backups of your `AccountData.json` file if you use password encryption.
