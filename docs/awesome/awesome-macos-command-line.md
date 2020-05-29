<div class="github-widget" data-repo="herrbischoff/awesome-macos-command-line"></div>
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><ins class="adsbygoogle" style="display:block" data-ad-client="ca-pub-6890694312814945" data-ad-slot="5473692530" data-ad-format="auto"  data-full-width-responsive="true"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
<h1><img src="https://cdn.rawgit.com/herrbischoff/awesome-macos-command-line/cab824f0/assets/logo.svg" alt="Awesome macOS Command Line" width="600"></h1>

&gt;专门针对OS X的Shell命令和工具的精选列表.
>
 &gt; _“您不必了解所有内容.  您只需要知道在必要时在哪里可以找到它.”  （约翰·布鲁纳）_

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![Build Status](https://travis-ci.org/herrbischoff/awesome-macos-command-line.svg?branch=master)](https://travis-ci.org/herrbischoff/awesome-macos-command-line)

 如果您想做出贡献，强烈建议您这样做.  请阅读 [contribution guidelines](https://github.com/herrbischoff/awesome-macos-command-line/blob/master/contributing.md).

有关终端外壳的更多信息，请参见此列表的姐妹列表 [Awesome Command Line Apps](https://github.com/herrbischoff/awesome-command-line-apps).


## Caffeinating

 如果您在这里找到有用的东西，可以给我买杯咖啡.  我花了很多时间和精力来整理这份清单.  让我保持适当的咖啡因会加速事情的发展.  这真的会让我开心.  陌生人之类的善良.  如果您不能或不愿意，那就没有难过的感觉.  由于某种原因，它是完全免费的.  尽管如此，那还是很棒的.

<a href="https://www.buymeacoffee.com/Oi5LPJ4lr" target="_blank"><img src="https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>





## Appearance

### Transparency

#### Transparency in Menu and Windows
```bash
## Reduce Transparency
默认写com.apple.universalaccess reduceTransparency -bool true

## Restore Default Transparency
默认写com.apple.universalaccess reduceTransparency -bool false
```


### Wallpaper

#### Set Wallpaper
```bash
## Up to Mountain Lion
osascript -e&#39;告诉应用程序“ Finder”将桌面图片设置为POSIX文件“ /path/to/picture.jpg”&#39;

## Since Mavericks
sqlite3〜/ Library / Application \ Support / Dock / desktoppicture.db“更新数据集值=&#39;/path/to/picture.jpg&#39;” &amp;&amp; killall Dock
```


## Applications

### App Store

#### List All Apps Downloaded from App Store

```bash
## Via find
find /Applications -path '*Contents/_MASReceipt/receipt' -maxdepth 4 -print |\sed 's#.app/Contents/_MASReceipt/receipt#.app#g; s#/Applications/##'

## Via Spotlight
mdfind kMDItemAppStoreHasReceipt = 1
```

#### Show Debug Menu
适用于优胜美地.
```bash
## Enable
默认写com.apple.appstore ShowDebugMenu -bool true

## Disable (Default)
默认写com.apple.appstore ShowDebugMenu -bool false
```


### Apple Remote Desktop

#### Kickstart Manual Pages
```bash
sudo /系统/库/CoreServices/RemoteManagement/ARDAgent.app/Contents/Resources/kickstart -help
```

#### Activate And Deactivate the ARD Agent and Helper
```bash
## Activate And Restart the ARD Agent and Helper
sudo /系统/库/CoreServices/RemoteManagement/ARDAgent.app/Contents/Resources/kickstart -activate -restart -agent -console

## Deactivate and Stop the Remote Management Service
sudo /系统/库/CoreServices/RemoteManagement/ARDAgent.app/Contents/资源/ kickstart-停用-停止
```

#### Enable and Disable Remote Desktop Sharing
```bash
## Allow Access for All Users and Give All Users Full Access
sudo /系统/库/CoreServices/RemoteManagement/ARDAgent.app/Contents/Resources/kickstart -configure -allowAccessFor -allUsers -privs -all

## Disable ARD Agent and Remove Access Privileges for All Users
sudo /系统/库/CoreServices/RemoteManagement/ARDAgent.app/Contents/Resources/kickstart-停用-配置-访问-关闭
```

#### Remove Apple Remote Desktop Settings
```bash
 须藤rm -rf / var / db / RemoteManagement;  \
 sudo默认删除/Library/Preferences/com.apple.RemoteDesktop.plist;  \
 默认为delete〜/ Library / Preferences / com.apple.RemoteDesktop.plist;  \
 sudo rm -r / Library / Application \ Support / Apple / Remote \ Desktop /;  \
 rm -r〜/ Library / Application \ Support / Remote \ Desktop /;  \
rm -r〜/ Library / Containers / com.apple.RemoteDesktop
```

### Contacts

#### Debug Mode
```bash
## Enable
默认写com.apple.addressbook ABShowDebugMenu -bool true

## Disable (Default)
默认写com.apple.addressbook ABShowDebugMenu -bool false
```

### Google

#### Uninstall Google Update
```bash
〜/ Library / Google / GoogleSoftwareUpdate / GoogleSoftwareUpdate.bundle / Contents / Resources / ksinstall --nuke
```

### iTunes

#### Keyboard Media Keys
 这适用于优胜美地.  El Capitan中引入了系统完整性保护，可防止卸载系统启动代理.
```bash
## Stop Responding to Key Presses
launchctl卸载-w /System/Library/LaunchAgents/com.apple.rcd.plist

## Respond to Key Presses (Default)
launchctl load -w /System/Library/LaunchAgents/com.apple.rcd.plist
```

 从El Capitan开始，您可以禁用SIP或诉诸某种黑客手段，这将使任何用户无法访问iTunes，从而有效地阻止了iTunes自身或助手的启动.  请注意，出于所有目的和目的，这将破坏iTunes的安装，并可能与以后的OS更新冲突.
```bash
sudo chmod 0000 /应用程序/iTunes.app
```

### Mail

#### Show Attachments as Icons

```bash
默认写com.apple.mail DisableInlineAttachmentViewing -bool是
```

#### Vacuum Mail Index
 下面的AppleScript代码将退出Mail，清理SQLite索引，然后重新打开Mail.  在尚未经过优化的大型电子邮件数据库上，这可以显着提高响应速度和速度.
```applescript
(*
通过清除信封索引来加速Mail.app
来自以下网址的代码：http：//web.archive.org/web/20071008123746/http：//www.hawkwings.net/2007/03/03/scripts-to-automate-the-mailapp-envelope-speed-trick/
最初由“ pmbuko”修改，由Romulo修改
由Brett Terpstra更新于2012
由MathiasTörnblom2015更新，以支持El Capitan中的V3，并且仍保持向后兼容性
Updated by Andrei Miclaus 2017 to support V4 in Sierra
*)

tell application "Mail" to quit
设置os_version以执行shell脚本“ sw_vers -productVersion”
将mail_version设置为“ V2”
考虑数字字符串
    如果“ 10.10” &lt;= os_version，则将mail_version设置为“ V3”
    如果“ 10.12” &lt;= os_version，则将mail_version设置为“ V4”
    如果“ 10.13” &lt;= os_version，则将mail_version设置为“ V5”
    如果“ 10.14” &lt;= os_version，则将mail_version设置为“ V6”
结束考虑

设置sizeBefore做外壳程序脚本“ ls -lnah〜/ Library / Mail /”＆mail_version＆“ / MailData | grep -E&#39;信封索引$&#39;| awk {&#39;print $ 5&#39;}”
做shell脚本“ / usr / bin / sqlite3〜/ Library / Mail /”和mail_version和“ / MailData / Envelope \\ Index vacuum”

设置sizeAfter做外壳程序脚本“ ls -lnah〜/ Library / Mail /”和mail_version＆“ / MailData | grep -E&#39;信封索引$&#39;| awk {&#39;打印$ 5&#39;}”

显示对话框（“之前的邮件索引：”＆sizeBefore＆return＆“之后的邮件索引：”＆sizeAfter＆return＆return＆“享受新速度！”）

告诉应用程序“邮件”激活
```

### Safari

#### Change Default Fonts
```bash
默认写com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2StandardFontFamily Georgia
默认写入com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DefaultFontSize 16
默认写com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2FixedFontFamily Menlo
默认写com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DefaultFixedFontSize 14
```

#### Enable Develop Menu and Web Inspector
```bash
默认写com.apple.Safari IncludeInternalDebugMenu -bool true &amp;&amp; \
默认写com.apple.Safari IncludeDevelopMenu -bool true &amp;&amp; \
默认写com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true &amp;&amp; \
默认写com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true &amp;&amp; \
默认写-g WebKitDeveloperExtras -bool true
```

#### Get Current Page Data
其他选项：“获取来源”，“获取文字”.
```bash
osascript -e&#39;告诉应用程序“ Safari”以获取前窗当前选项卡的URL”
```

#### Use Backspace/Delete to Go Back a Page
```bash
## Enable
默认写com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2BackspaceKeyNavigationEnabled -bool是

## Disable
默认写入com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2BackspaceKeyNavigationEnabled -bool否
```

### Sketch

#### Export Compact SVGs
```bash
默认写com.bohemiancoding.sketch3 exportCompactSVG -bool是
```

### Skim

#### Turn Off Auto Reload Dialog
删除对话框，默认为自动重新加载.
```bash
默认为write -app Skim SKAutoReloadFileUpdate -boolean true
```
### Terminal

#### Focus Follows Mouse
```bash
## Enable
默认设置为com.apple.Terminal FocusFollowsMo​​use -string是

## Disable
默认写com.apple.Terminal FocusFollowsMo​​use -string NO
```

### TextEdit

#### Use Plain Text Mode as Default
```bash
默认写com.apple.TextEdit RichText -int 0
```

### Visual Studio Code

#### Fix VSCodeVim Key Repeat
```bash
默认写入com.microsoft.VSCode ApplePressAndHoldEnabled -bool false
```

## Backup

### Time Machine

#### Change Backup Interval
 这会将间隔更改为30分钟.  整数值是以秒为单位的时间.
```bash
sudo默认写入/System/Library/LaunchDaemons/com.apple.backupd-auto StartInterval -int 1800
```

#### Local Backups
Time Machine备份卷不可用时，Time Machine是否执行本地备份.
```bash
## Status
默认阅读/Library/Preferences/com.apple.TimeMachine MobileBackups

## Enable (Default)
须藤tmutil enablelocal

## Disable
须藤tmutil disablelocal
```

 从High Sierra开始，您不能禁用本地快照.  现在，Time Machine始终创建本地APFS快照，并使用该快照作为数据源来创建常规备份，而不是像HFS格式化磁盘那样使用活动磁盘作为源.

#### Prevent Time Machine from Prompting to Use New Hard Drives as Backup Volume
```bash
sudo默认写入/Library/Preferences/com.apple.TimeMachine DoNotOfferNewDisksForBackup -bool true
```

#### Show Time Machine Logs
这个小脚本将输出Time Machine活动的最后12个小时，然后输出实时活动.
```bash
#!/bin/sh

filter =&#39;processImagePath包含“ backupd”，并且子系统以“ com.apple.TimeMachine”开头

## show the last 12 hours
start =“ $（date -j -v-12H +&#39;％Y-％m-％d％H：％M：％S&#39;）”

回声“”
回声“ [历史（从$开始）]”
回声“”

日志显示--style syslog --info --start“ $ start”-谓词“ $ filter”

回声“”
回声“ [以下]”
回声“”

日志流--style syslog --info --predicate“ $ filter”
```

#### Toggle Backup While on Battery
```bash
## Status
sudo默认阅读/Library/Preferences/com.apple.TimeMachine需要ACPower

## Enable (Default)
sudo默认写入/Library/Preferences/com.apple.TimeMachine RequiresACPower -bool true

## Disable
sudo默认写入/Library/Preferences/com.apple.TimeMachine要求ACPower -bool false
```

#### Verify Backup
 从OS X 10.11开始，Time Machine记录复制到快照中的文件的校验和.  对于由早期版本的OS X复制的文件，不会追溯计算校验和.
```bash
sudo tmutil verifychecksums /路径/到/备份
```

## Developer

### Vim

#### Compile Sane Vim
通过Homebrew编译MacVim的所有代码，包括覆盖系统Vim.
```bash
brew install macvim --HEAD
```

#### Neovim
通过Homebrew安装现代的Vim替代方案.
```bash
brew install neovim
```

### Xcode

#### Install Command Line Tools without Xcode
```bash
xcode-select-安装
```

#### Remove All Unavailable Simulators
```bash
xcrun simctl删除不可用
```


## Dock

#### Add a Stack with Recent Applications
```bash
 默认写com.apple.dock持久其他-array-add&#39;{“ tile-data” = {“” list-type“ = 1;  };  “ tile-type” =“最近的瓷砖”；  }&#39;&amp;&amp; \
杀人码头
```

#### Add a Nameless Stack Folder and Small Spacer
```bash
 默认写com.apple.dock持久其他-array-add&#39;{“ tile-data” = {};  “ tile-type” =“小垫片-瓷砖”;  }&#39;&amp;&amp; \
杀人码头
```

#### Add a Space
```bash
默认写com.apple.dock持久应用程序-array-add&#39;{“ tile-type” =“ spacer-tile”;}&#39;&amp;&amp; \
杀人码头
```

#### Add a Small Space
```bash
默认写com.apple.dock持久应用程序-array-add&#39;{“ tile-type” =“ small-spacer-tile”;}&#39;&amp;&amp; \
杀人码头
```

#### Auto Rearrange Spaces Based on Most Recent Use
```bash
## Enable (Default)
默认写com.apple.dock mru-spaces -bool true &amp;&amp; \
杀人码头

## Disable
默认写com.apple.dock mru-spaces -bool false &amp;&amp; \
杀人码头
```

#### Autohide

bash
## Enable
默认写com.apple.dock autohide -bool true &amp;&amp; \
杀人码头

## Disable (Default)
默认写com.apple.dock autohide -bool false &amp;&amp; \
杀人码头
```

#### Icon Bounce
全局设置当相应的应用程序需要您关注时，是否应停靠Dock图标.
```bash
## Enable (Default)
默认写com.apple.dock不反弹-bool true &amp;&amp; \
杀人码头

## Disable
默认写com.apple.dock不反弹-bool false &amp;&amp; \
杀人码头
```

#### Lock the Dock Size
```bash
## Enable
默认写com.apple.Dock大小不可变-bool是&amp;&amp; \
杀人码头

## Disable (Default)
默认写com.apple.Dock大小不可变-bool否&amp;&amp; \
杀人码头
```

#### Reset Dock
```bash
默认删除com.apple.dock &amp;&amp; \
杀人码头
```

#### Resize
 完全调整码头的大小.  要调整大小，请将“ 0”值更改为整数.
```bash
默认写com.apple.dock tileize -int 0 &amp;&amp; \
杀人码头
```

#### Scroll Gestures
 使用触摸板或鼠标滚轮与Dock项进行交互.  允许您使用向上滚动手势来打开堆栈.  在正在运行的应用程序上使用相同的手势将调用Exposé/ Mission Control.
```bash
## Enable
默认写com.apple.dock滚动到打开-bool true &amp;&amp; \
杀人码头

## Disable (Default)
默认写com.apple.dock滚动到打开-bool false &amp;&amp; \
杀人码头
```

#### Set Auto Show/Hide Delay
浮点数定义了显示/隐藏延迟（以毫秒为单位）.
```bash
默认写com.apple.dock autohide-time-modifier -float 0.4 &amp;&amp; \
默认写com.apple.dock autohide-delay -float 0 &amp;&amp; \
杀人码头
```

#### Show Hidden App Icons
```bash
## Enable
默认写com.apple.dock showhidden -bool true &amp;&amp; \
杀人码头

## Disable (Default)
默认写com.apple.dock showhidden -bool false &amp;&amp; \
杀人码头
```

#### Show Only Active Applications
```bash
## Enable
默认写com.apple.dock仅静态-bool true &amp;&amp; \
杀人码头

## Disable (Default)
默认写com.apple.dock仅静态-bool false &amp;&amp; \
杀人码头
```

#### Single App Mode
单击Dock中的应用程序图标时，将出现相应的窗口
到最前面，但所有其他应用程序窗口将被隐藏.
```bash
## Enable
默认写com.apple.dock单应用程序-bool true &amp;&amp; \
杀人码头

## Disable (Default)
默认写com.apple.dock单应用程序-bool false &amp;&amp; \
杀人码头
```


## Documents

#### Convert File to HTML
支持的格式为纯文本，富文本（rtf）和Microsoft Word（doc / docx）.
```bash
textutil-转换html file.ext
```


## Files, Disks and Volumes

#### Create an Empty File
创建一个空的10 GB测试文件.
```bash
mkfile 10g / path / to / file
```

#### Disable Sudden Motion Sensor
使用SSD时，将其保持打开状态是没有用的.
```bash
须藤pmset -a sms 0
```

#### Eject All Mountable Volumes
唯一可靠的方法是将AppleScript命令发送到Finder.
```bash
osascript -e&#39;告诉应用程序“ Finder”弹出（每个可弹出的磁盘为true的磁盘）”
```

#### Repair File Permissions
您不必为此使用“磁盘工具” GUI.
```bash
sudo diskutil repairPermissions /
```
 &gt;从OS X El Capitan开始，系统文件权限得到自动保护.  不再需要使用“磁盘工具”来验证或修复权限.  （[Source](https://support.apple.com/en-us/HT201560))

#### Set Boot Volume
```bash
## Up to Yosemite
保佑--mount“ / path / to / mount / volume” --setBoot

## From El Capitan
sudo systemsetup -setstartupdisk /系统/库/ CoreServices
```

#### Show All Attached Disks and Partitions
```bash
有争议的艺术
```

#### View File System Usage
文件系统访问信息的连续流.
```bash
须藤fs_usage
```
### APFS

 自High Sierra开始提供.  没有中央实用程序，用法不一致，因为大多数功能都已整合到`tmutil`中.

#### Convert Volume from HFS+ to APFS
```bash
/System/Library/Filesystems/apfs.fs/Contents/Resources/hfs_convert / path / to / file / system
```

#### Create New APFS Filesystem
```bash
/System/Library/Filesystems/apfs.fs/Contents/Resources/newfs_apfs / path / to / device
```

#### Create Snapshot
```bash
tmutil localsnapshot
```

#### Delete Snapshot
```bash
tmutil deletelocalsnapshots com.apple.TimeMachine.2018-01-26-044042
````

#### List Snapshots
```bash
tmutil listlocals快照/
```

#### Mount Snapshot
快照是只读的.
```bash
mkdir〜/ mnt
/System/Library/Filesystems/apfs.fs/Contents/Resources/mount_apfs -s com.apple.TimeMachine.2018-01-26-044042 /〜/ mnt
```

### Disk Images

```bash
hdiutil create -volname“卷名” -srcfolder / path / to / folder -ov diskimage.dmg
```

如果要加密磁盘映像：
```bash
hdiutil create -encryption -stdinpass -volname“卷名” -srcfolder / path / to / folder -ov crypto.dmg
```

 默认情况下，系统会提示您输入密码.  您可以通过输入密码来自动执行此操作：
```bash
 echo -n YourPassword |  hdiutil create -encryption -stdinpass -volname“卷名” -srcfolder / path / to / folder -ov crypto.dmg
```

#### Burn Disk Images to DVD
此命令适用于.iso，.img和.dmg图像.
```bash
hdiutil刻录/ path / to / image_file
```

#### Disable Disk Image Verification
```bash
默认写com.apple.frameworks.diskimages skip-verify -bool true &amp;&amp; \
默认写com.apple.frameworks.diskimages skip-verify-locked -bool true &amp;&amp; \
默认写com.apple.frameworks.diskimages skip-verify-remote -bool true
```

#### Make Volume OS X Bootable
```bash
bless --folder“ /路径/到/已挂载/卷/系统/库/ CoreServices” --bootinfo --bootefi
```

#### Mount Disk Image
```bash
hdiutil附加/path/to/diskimage.dmg
```

#### Unmount Disk Image
```bash
hdiutil分离/ dev / disk2s1
```

#### Write Disk Image to Volume
就像磁盘工具的“还原”功能.
```bash
Sudo ASR-还原-noverify-源/path/to/diskimage.dmg-目标/卷/ VolumeToRestoreTo
```


## Finder

### Desktop

#### Show External Media
外部HD，拇指驱动器等
```bash
## Enable
默认写com.apple.finder ShowExternalHardDrivesOnDesktop -bool true &amp;&amp; \
Killall搜寻器

## Disable (Default)
默认写com.apple.finder ShowExternalHardDrivesOnDesktop -bool false &amp;&amp; \
Killall搜寻器
```

#### Show Internal Media
内置HD或SSD.
```bash
## Enable
默认写com.apple.finder ShowHardDrivesOnDesktop -bool true &amp;&amp; \
Killall搜寻器

## Disable (Default)
默认写com.apple.finder ShowHardDrivesOnDesktop -bool false &amp;&amp; \
Killall搜寻器
```

#### Show Removable Media
CD，DVD，iPod等
```bash
## Enable
默认写com.apple.finder ShowRemovableMediaOnDesktop -bool true &amp;&amp; \
Killall搜寻器

## Disable (Default)
默认写com.apple.finder ShowRemovableMediaOnDesktop -bool false &amp;&amp; \
Killall搜寻器
```

#### Show Network Volumes
AFP，SMB，NFS，WebDAV等
```bash
## Enable
默认写com.apple.finder ShowMountedServersOnDesktop -bool true &amp;&amp; \
Killall搜寻器

## Disable (Default)
默认写com.apple.finder ShowMountedServersOnDesktop -bool false &amp;&amp; \
Killall搜寻器
```

### Files and Folders

#### Clear All ACLs
```bash
须藤chmod -RN / path / to / folder
```

#### Hide Folder in Finder
```bash
chflags隐藏/ path / to / folder /
```
#### Show All File Extensions
```bash
默认写-g AppleShowAllExtensions -bool true
```

#### Show Hidden Files
```bash
## Show All
默认写入com.apple.finder AppleShowAllFiles true

## Restore Default File Visibility
默认写com.apple.finder AppleShowAllFiles false
```

#### Remove Protected Flag
```bash
sudo chflags -R nouchg /路径/到/文件/或/文件夹
```

#### Show Full Path in Finder Title
```bash
默认写com.apple.finder _FXShowPosixPathInTitle -bool true
```

#### Unhide User Library Folder
```bash
chflags nohidden〜/库
```

#### Increase Number of Recent Places
```bash
默认写-g NSNavRecentPlacesLimit -int 10 &amp;&amp; \
Killall搜寻器
```

### Layout

#### Show "Quit Finder" Menu Item
可以使用默认的快捷键<kbd>Cmd</kbd> + <kbd>Q</kbd>来查看Finder菜单项“ Quit Finder”.
```bash
## Enable
默认写com.apple.finder QuitMenuItem -bool true &amp;&amp; \
Killall搜寻器

## Disable (Default)
默认写com.apple.finder QuitMenuItem -bool false &amp;&amp; \
Killall搜寻器
```

#### Smooth Scrolling
如果您使用的旧Mac会使动画混乱，则很有用.
```bash
## Disable
默认为write -g NSScrollAnimationEnabled -bool false

## Enable (Default)
默认为write -g NSScrollAnimationEnabled -bool true
```

#### Rubberband Scrolling
```bash
## Disable
默认为write -g NSScrollViewRubberbanding -bool false

## Enable (Default)
默认为write -g NSScrollViewRubberbanding -bool true
```

#### Expand Save Panel by Default
```bash
默认写-g NSNavPanelExpandedStateForSaveMode -bool true &amp;&amp; \
默认写-g NSNavPanelExpandedStateForSaveMode2 -bool true
```

#### Desktop Icon Visibility
```bash
## Hide Icons
默认写com.apple.finder CreateDesktop -bool false &amp;&amp; \
Killall搜寻器

## Show Icons (Default)
默认写com.apple.finder CreateDesktop -bool true &amp;&amp; \
Killall搜寻器
```

#### Path Bar
```bash
## Show
默认写com.apple.finder ShowPathbar -bool true

## Hide (Default)
默认写com.apple.finder ShowPathbar -bool false
```

#### Scrollbar Visibility
可能的值：“ WhenScrolling”，“ Automatic”和“ Always”.
```bash
默认写-g AppleShowScrollBars -string“始终”
```

#### Status Bar
```bash
## Show
默认写com.apple.finder ShowStatusBar -bool true

## Hide (Default)
默认写com.apple.finder ShowStatusBar -bool false
```

#### Save to Disk by Default
将默认保存目标设置为本地磁盘，而不是iCloud.
```bash
默认写-g NSDocumentSaveNewDocumentsToCloud -bool false
```

#### Set Current Folder as Default Search Scope
```bash
默认写com.apple.finder FXDefaultSearchScope -string“ SCcf”
```

#### Set Default Finder Location to Home Folder
```bash
默认写com.apple.finder NewWindowTarget -string“ PfLo” &amp;&amp; \
默认写com.apple.finder NewWindowTargetPath -string“ file：// $ {HOME}”
```

#### Set Sidebar Icon Size
将尺寸设置为“中”.
```bash
默认写-g NSTableViewDefaultSizeMode -int 2
```

### Metadata Files

#### Disable Creation of Metadata Files on Network Volumes
避免创建.DS_Store和AppleDouble文件.
```bash
默认写com.apple.desktopservices DSntWriteNetworkStores -bool true
```

#### Disable Creation of Metadata Files on USB Volumes
避免创建.DS_Store和AppleDouble文件.
```bash
默认写入com.apple.desktopservices DSntWriteUSBStores -bool true
```

### Opening Things

#### Change Working Directory to Finder Path
如果打开了多个窗口，它将选择最上面的一个.
```bash
cd“ $（osascript -e&#39;tell app“ Finder”到（插入位置作为别名的）POSIX路径&#39;）”
```

#### Open URL
```bash
打开https://github.com
```

#### Open File
```bash
打开README.md
```

#### Open Applications
您可以使用-a打开应用程序.
```bash
打开-a“ Google Chrome” https://github.com
```

#### Open Folder
```bash
打开/路径/到/文件夹/
```

#### Open Current Folder
```bash
打开.
```


## Fonts

#### Clear Font Cache for Current User
要清除所有用户的字体缓存，请在此命令前放置sudo.
```bash
atsutil数据库-removeUser &amp;&amp; \
atsutil服务器-shutdown &amp;&amp; \
atsutil服务器-ping
```

#### Get SF Mono Fonts
 您需要下载并安装Xcode 8 beta才能正常工作.  之后，它们应在所有应用程序中可用.
```bash
cp -v /Applications/Xcode-beta.app/Contents/SharedFrameworks/DVTKit.framework/Versions/A/Resources/Fonts/SFMono-*〜/ Library / Fonts
```

从Sierra开始，它们包含在Terminal.app中.
```bash
cp -v /应用程序/实用程序/Terminal.app/内容/资源/字体/ SFMono- *〜/库/字体
```

从Catalina开始，Utilities应用程序（包括Terminal.app）现在位于“ / System”文件夹中.
```bash
cp -v /系统/应用程序/实用程序/Terminal.app/内容/资源/字体/ SFMono- *〜/库/字体
```

## Functions

请参阅 [this file](https://github.com/herrbischoff/awesome-macos-command-line/blob/master/functions.md).


## Hardware

### Bluetooth

```bash
## Status
默认读取/Library/Preferences/com.apple.Bluetooth ControllerPowerState

## Enable (Default)
sudo默认写入/Library/Preferences/com.apple.Bluetooth ControllerPowerState -int 1

## Disable
sudo默认写入/Library/Preferences/com.apple.Bluetooth ControllerPowerState -int 0 &amp;&amp; \
须藤killall -HUP蓝色
```

### Harddisks

#### Force Enable Trim
 为非Apple SSD启用Trim.  自优胜美地以来，此命令可用.
```bash
forcetrim
```

### Hardware Information

#### List All Hardware Ports
```bash
networksetup -listall硬件端口
```

#### Remaining Battery Percentage
```bash
 pmset -g batt |  egrep“（[[0-9] + \％）.*” -o --colour = auto |  切-f1 -d&#39;;&#39;
```

#### Remaining Battery Time
```bash
 pmset -g batt |  egrep“（[[0-9] + \％）.*” -o --colour = auto |  切-f3 -d&#39;;&#39;
```

#### Show Connected Device's UDID
```bash
 system_profiler SPUSBDataType |  sed -n -e&#39;/ iPad /，/ Serial / p&#39;-e&#39;/ iPhone /，/ Serial / p&#39;
```

#### Show Current Screen Resolution
```bash
 system_profiler SPDisplaysDataType |  grep分辨率
```

#### Show CPU Brand String
```bash
sysctl -n machdep.cpu.brand_string
```

### Infrared Receiver

```bash
## Status
默认读取/Library/Preferences/com.apple.driver.AppleIRController DeviceEnabled

## Enable (Default)
默认写入/Library/Preferences/com.apple.driver.AppleIRController DeviceEnabled -int 1

## Disable
默认写入/Library/Preferences/com.apple.driver.AppleIRController DeviceEnabled -int 0
```

### Power Management

#### Prevent System Sleep
防止睡眠1小时：
```bash
咖啡因-u -t 3600
```

#### Show All Power Management Settings
```bash
须藤pmset -g
```

#### Put Display to Sleep after 15 Minutes of Inactivity
```bash
须藤pmset displaysleep 15
```

#### Put Computer to Sleep after 30 Minutes of Inactivity
```bash
须藤pmset睡眠30
```

#### Check System Sleep Idle Time
```bash
sudo systemsetup -getcomputersleep
```

#### Set System Sleep Idle Time to 60 Minutes
```bash
sudo systemsetup -setcomputersleep 60
```

#### Turn Off System Sleep Completely
```bash
sudo systemsetup -setcomputersleep从不
```

#### Automatic Restart on System Freeze
```bash
sudo systemsetup -setrestartfreeze在
```

#### Chime When Charging
连接MagSafe时播放iOS充电声音.
```bash
## Enable
默认写com.apple.PowerChime ChimeOnAllHardware -bool true &amp;&amp; \
打开/System/Library/CoreServices/PowerChime.app

## Disable (Default)
默认写com.apple.PowerChime ChimeOnAllHardware -bool false &amp;&amp; \
杀死所有力量
```


## Input Devices

### Keyboard

#### Auto-Correct
```bash
## Disable
默认为write -g NSAutomaticSpellingCorrectionEnabled -bool false

## Enable (Default)
默认为write -g NSAutomaticSpellingCorrectionEnabled -bool true

## Show Status
默认读取为-g NSAutomaticSpellingCorrectionEnabled
```

#### Full Keyboard Access
在模式对话框中启用选项卡.
```bash
## Text boxes and lists only (Default)
默认写入NSGlobalDomain AppleKeyboardUIMode -int 0

## All controls
默认写入NSGlobalDomain AppleKeyboardUIMode -int 3
```

#### Key Repeat
禁用默认的“按住”行为.
```bash
## Enable Key Repeat
默认写-g ApplePressAndHoldEnabled -bool false

## Disable Key Repeat
默认写-g ApplePressAndHoldEnabled -bool true
```

#### Key Repeat Rate
Sets a very fast repeat rate, adjust to taste.
```bash
默认写-g KeyRepeat -int 0.02
```

## Launchpad

#### Reset Launchpad Layout
您需要重新启动`Dock`，因为Launchpad已绑定到它.
```bash
## Up to Yosemite
rm〜/ Library / Application \ Support / Dock / *.db &amp;&amp; \
杀人码头

## From El Capitan
默认写com.apple.dock ResetLaunchPad -bool true &amp;&amp; \
杀人码头
```

## Media

### Audio

#### Convert Audio File to iPhone Ringtone
```bash
afconvert input.mp3铃声.m4r -f m4af
```

#### Create Audiobook From Text
使用“ Alex”语音，这是一种普通的UTF-8编码文本文件，用于输入和AAC输出.
```bash
说-v Alex -f file.txt -o“ output.m4a”
```

#### Disable Sound Effects on Boot
```bash
sudo nvram SystemAudioVolume =“”
```

#### Mute Audio Output
```bash
osascript -e&#39;设置音量输出静音为真&#39;
```

#### Set Audio Volume
```bash
osascript -e&#39;设置音量4&#39;
```

#### Play Audio File
您可以播放QuickTime本身支持的所有音频格式.
```bash
afplay -q 1文件名.mp3
```

#### Speak Text with System Default Voice
```bash
说“您的所有基地都属于我们！”
```

#### Startup Chime
较旧的Mac：
```bash
## Enable (Default)
sudo nvram BootAudio =％01

## Disable
sudo nvram BootAudio =％00
```

从2016年型号开始：
```bash
## Enable
sudo nvram StartupMute =％00

## Disable (Default)
sudo nvram StartupMute =％01
```

### Video

#### Auto-Play Videos in QuickTime Player
```bash
默认写入com.apple.QuickTimePlayerX MGPlayMovieOnOpen 1
```


## Networking

### Bonjour

#### Bonjour Service
```bash
## Disable
sudo默认写/System/Library/LaunchDaemons/com.apple.mDNSResponder.plist ProgramArguments -array-add“ -NoMulticastAdvertisements”

## Enable (Default)
sudo默认写/System/Library/LaunchDaemons/com.apple.mDNSResponder.plist ProgramArguments -array“ / usr / sbin / mDNSResponder”“ -launchd”
```

### DHCP

#### Renew DHCP Lease
```bash
sudo ipconfig设置en0 DHCP
```

#### Show DHCP Info
```bash
ipconfig getpacket zh-CN
```

### DNS

#### Clear DNS Cache
```bash
sudo dscacheutil -flushcache &amp;&amp; \
须藤killall -HUP mDNSResponder
```

### Hostname

#### Set Computer Name/Host Name
```bash
sudo scutil --set ComputerName "newhostname" && \
sudo scutil --set主机名“ newhostname” &amp;&amp; \
sudo scutil --set LocalHostName“ newhostname” &amp;&amp; \
sudo默认写/Library/Preferences/SystemConfiguration/com.apple.smb.server NetBIOSName -string“ newhostname”
```

### Network Preferences

#### Network Locations
在“网络”首选项窗格中创建的网络位置之间切换.
```bash
## Status
scselect

## Switch Network Location
scselect LocationNameFromStatus
```

#### Set Static IP Address
```bash
networksetup -setmanual“ Ethernet” 192.168.2.100 255.255.255.0 192.168.2.1
```

### Networking Tools

#### Ping a Host to See Whether It’s Available
```bash
ping -o github.com
```

#### Troubleshoot Routing Problems
```bash
traceroute github.com
```

### SSH

#### Permanently Add Private Key Passphrase to SSH Agent
 &gt;在macOS Sierra之前，ssh将显示一个对话框，询问您的密码短语，并提供将其存储到钥匙串中的选项.  此用户界面在一段时间前已过时，已被删除.
>
 &gt;而是在macOS Sierra中引入了新的UseKeychain选项，允许用户指定是否希望将密码存储在钥匙串中.  默认情况下，此选项已在macOS Sierra上启用，这导致所有密码短语都存储在钥匙串中.
>
 &gt;这不是预期的默认行为，因此在macOS 10.12.2中已对此进行了更改.  （[Source](https://developer.apple.com/library/archive/technotes/tn2449/_index.html))
```bash
ssh-add -K / path / to / private_key
```
然后添加到`〜/ .ssh / config`中：
```bash
主机server.example.com
    IdentityFile / path / to / private_key
    UseKeychain是
```

#### Remote Login
```bash
## Enable remote login
sudo launchctl加载-w /System/Library/LaunchDaemons/ssh.plist

## Disable remote login
sudo launchctl卸载-w /System/Library/LaunchDaemons/ssh.plist
```

### TCP/IP

#### Show Application Using a Certain Port
这将输出当前使用端口80的所有应用程序.
```bash
须藤lsof -i：80
```

#### Show External IP Address
如果您的ISP不替换DNS请求（不应该），则可以使用.
```bash
挖+短myip.opendns.com @ resolver1.opendns.com
```
适用于所有网络的替代方案.
```bash
curl -s https://api.ipify.org &amp;&amp;回声
```

#### Show Network Interface Information
`scutil`命令的未记录标志.
```bash
scutil --nwi
```

### TFTP

#### Start Native TFTP Daemon
文件将从`/ private / tftpboot`提供.
```bash
sudo launchctl加载-F /System/Library/LaunchDaemons/tftp.plist &amp;&amp; \
sudo launchctl启动com.apple.tftpd
```

### Wi-Fi

#### Join a Wi-Fi Network
```bash
networksetup -setairportnetwork en0 WIFI_SSID WIFI_PASSWORD
```

#### Scan Available Access Points
创建指向airport命令的符号链接，以方便访问：
```bash
sudo ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport / usr / local / bin / airport
```
运行无线扫描：
```bash
机场-s
```

#### Show Current SSID
```bash
 /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport -I |  awk&#39;/ SSID / {print substr（$ 0，index（$ 0，$ 2））}&#39;
```

#### Show Local IP Address
```bash
ipconfig getifaddr zh-CN0
```

#### Show Wi-Fi Connection History
```bash
 默认读取/Library/Preferences/SystemConfiguration/com.apple.airport.preferences |  grep LastConnected -A 7
```

#### Show Wi-Fi Network Passwords
用您要从中查询密码的接入点的SSID交换SSID.
```bash
security find-generic-password -D "AirPort network password" -a "SSID" -gw
```

#### Turn on Wi-Fi Adapter
```bash
启用networksetup -setairportpower en0
```

## Package Managers

- [Fink](http://www.finkproject.org)  -用于Darwin的Unix开源软件的完整世界.  有点过时了.
- [Homebrew](https://brew.sh) -缺少OS X的软件包管理器.最受欢迎的选择.
- [MacPorts](https://www.macports.org)  -编译，安装和升级命令行，基于X11或Aqua的开源软件.  很干净，这就是我用的.

### Homebrew

#### Full Uninstall

```bash
ruby -e“ $（curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall）”
```


## Printing

#### Clear Print Queue
```bash
取消-a-
```

#### Expand Print Panel by Default
```bash
默认写-g PMPrintingExpandedStateForPrint -bool true &amp;&amp; \
默认写-g PMPrintingExpandedStateForPrint2 -bool true
```

#### Quit Printer App After Print Jobs Complete
```bash
默认写com.apple.print.PrintingPrefs“完成后退出” -bool true
```


## Security

### Application Firewall

#### Firewall Service
```bash
## Show Status
须藤/ usr / libexec / ApplicationFirewall / socketfilterfw --getglobalstate

## Enable
sudo / usr / libexec / ApplicationFirewall / socketfilterfw --setglobalstate在

## Disable (Default)
sudo / usr / libexec / ApplicationFirewall / socketfilterfw --setglobalstate关闭
```

#### Add Application to Firewall
```bash
须藤/ usr / libexec / ApplicationFirewall / socketfilterfw --add / path / to / file
```

### Gatekeeper

#### Add Gatekeeper Exception
```bash
spctl-添加/path/to/Application.app
```

#### Remove Gatekeeper Exception
```bash
spctl-删除/path/to/Application.app
```

#### Manage Gatekeeper
对于令人讨厌的Catalina系统弹出窗口阻止非签名应用程序执行尤其有用.
```bash
## Status
spctl-状态

## Enable (Default)
sudo spctl --master-启用

## Disable
sudo spctl --master-禁用
```

### Passwords

#### Generate Secure Password and Copy to Clipboard
```bash
 LC_ALL = C tr -dc“ [：alnum：]” &lt;/ dev / urandom |  头-c 20 |  pbcopy
```

### Physical Access

#### Launch Screen Saver

```bash
## Up to Sierra
打开/System/Library/Frameworks/ScreenSaver.framework/Versions/A/Resources/ScreenSaverEngine.app

## From High Sierra
/System/Library/CoreServices/ScreenSaverEngine.app/Contents/MacOS/ScreenSaverEngine
```


#### Lock Screen
```bash
/ System / Library / CoreServices / Menu \ Extras / User.menu / Contents / Resources / CGSession -suspend
```

#### Screensaver Immediate Lock
```bash
## Status
默认读取com.apple.screensaver askForPasswordDelay

## Enable (Default)
默认写com.apple.screensaver askForPasswordDelay -int 0

## Disable (Integer = lock delay in seconds)
默认写com.apple.screensaver askForPasswordDelay -int 10
```

#### Screensaver Password
```bash
## Status
默认读取com.apple.screensaver askForPassword

## Enable
默认写com.apple.screensaver askForPassword -int 1

## Disable (Default)
默认写com.apple.screensaver askForPassword -int 0
```

### Wiping Data

 注意：在Mac OS 10.9之后，似乎已删除了srm命令.  有一个关于 [Apple support page](https://support.apple.com/en-us/HT201949) 暗示原因：
 &gt;对于SSD驱动器，“磁盘工具”中不提供“安全擦除”和“擦除可用空间”.  SSD驱动器不需要这些选项，因为标准擦除使其很难从SSD恢复数据.

#### Securely Remove File
```bash
srm /路径/到/文件
```

#### Securely Remove Folder
```bash
srm -r /路径/到/文件夹/
```

#### Securely Remove Path (Force)
```bash
srm -rf /路径/到/完成/破坏
```


## Search

### Find

#### Recursively Delete .DS_Store Files
```bash
 找 .  -type f -name&#39;* .DS_Store&#39;-ls -delete
```

### Locate

#### Build Locate Database
```bash
sudo launchctl加载-w /System/Library/LaunchDaemons/com.apple.locate.plist
```

#### Search via Locate
-i修饰符使搜索不区分大小写.
```bash
定位-i * .jpg
```


## System

### AirDrop

```bash
## Enable AirDrop over Ethernet and on Unsupported Macs
默认写com.apple.NetworkBrowser BrowseAllInterfaces -bool true

## Enable (Default)
默认情况下删除com.apple.NetworkBrowser DisableAirDrop

## Disable
默认写com.apple.NetworkBrowser DisableAirDrop -bool是
```

### AppleScript

#### Execute AppleScript
```bash
osascript /path/to/script.scpt
```

### Basics

#### Compare Two Folders
```bash
差异-qr / path / to / folder1 / path / to / folder2
```

#### Copy Large File with Progress
确保已安装“ pv”，并用适当的写入设备或文件替换“ / dev / rdisk2”.
```bash
 FILE = / path / to / file.iso pv -s $（du -h $ FILE | awk&#39;/.*/ {print $ 1}&#39;）$ FILE |  须藤dd of = / dev / rdisk2 bs = 1m
```

#### Restore Sane Shell
万一您的shell会话发疯（某些脚本或应用程序将其变成乱码）.
```bash
斯塔蒂·理智
```

#### Restart
```bash
须藤重启
```

#### Shutdown
```bash
须藤断电
```

#### Show Build Number of OS
```bash
sw_vers
```

#### Uptime
自上次重新启动以来已经过了多长时间.
```bash
uptime
```

### Clipboard

#### Copy data to Clipboard
```bash
 猫what.txt |  pbcopy
```

#### Convert Clipboard to Plain Text
```bash
 pbpaste |  textutil -convert txt -stdin -stdout -encoding 30 |  pbcopy
```

```bash
 pbpaste |  扩大|  pbcopy
```

#### Copy data from Clipboard
```bash
pbpaste&gt; what.txt
```

```bash
 pbpaste |  排序|  uniq |  pbcopy
```

### FileVault

#### Automatically Unlock FileVault on Restart
 如果在当前卷上启用了FileVault，它将绕过初始解锁重新启动系统.  该命令可能不适用于所有系统.
```bash
须藤fdesetup authrestart
```

#### FileVault Service
```bash
## Status
sudo fdesetup状态

## Enable
sudo fdesetup启用

## Disable (Default)
sudo fdesetup禁用
```

### Information/Reports

#### Generate Advanced System and Performance Report
```bash
sudo sysdiagnose -f〜/桌面/
```

### Installation

#### Create Bootable Installer
```bash
## Catalina
sudo / Applications / Install \ macOS \ Catalina.app/Contents/Resources/createinstallmedia --volume / Volumes / USB --nointeraction --downloadassets

## Mojave
sudo / Applications / Install \ macOS \ Mojave.app/Contents/Resources/createinstallmedia --volume / Volumes / USB --nointeraction --downloadassets

## High Sierra
sudo / Applications / Install \ macOS \ High \ Sierra.app/Contents/Resources/createinstallmedia --volume / Volumes / USB --applicationpath / Applications / Install \ macOS \ High \ Sierra.app

## Sierra
sudo / Applications / Install \ macOS \ Sierra.app/Contents/Resources/createinstallmedia --volume / Volumes / USB --applicationpath / Applications / Install \ macOS \ Sierra.app

## El Capitan
sudo / Applications / Install \ OS \ X \ El \ Capitan.app/Contents/Resources/createinstallmedia --volume / Volumes / USB --applicationpath / Applications / Install \ OS \ X \ El \ Capitan.app

## Yosemite
sudo / Applications / Install \ OS \ X \ Yosemite.app/Contents/Resources/createinstallmedia --volume / Volumes / USB --applicationpath / Applications / Install \ OS \ X \ Yosemite.app
```

*为了在擦除驱动器之前进行确认，请从命令中删除“ –-nointeraction”.
 * Mojave中新增了可选的––downloadassets标志.  它会下载安装过程中可能需要的资产，例如更新.
*自Mojave以来，不推荐使用––applicationpath标志，如果使用该标志将引发错误.

#### Download Older OS Versions

 版本|  代号|  下载
------------- | ------------- | --------
 Mac OS X 10.0 |  猎豹  不适用
 Mac OS X 10.1 |  彪马|  不适用
 Mac OS X 10.2 |  美洲虎|  在
 Mac OS X 10.3 |  豹|  不适用
 Mac OS X 10.4 |  老虎|  不适用
 Mac OS X 10.5 |  豹纹|  不适用
 Mac OS X 10.6 |  雪豹|  不适用
 Mac OS X 10.7 |  狮子|  不适用
 OS X 10.8 |  山狮|  不适用
 OS X 10.9 |  小牛|  不适用
OS X 10.10 |优胜美地| [Direct Download](http://updates-http.cdn-apple.com/2019/cert/061-41343-20191023-02465f92-3ab5-4c92-bfe2-b725447a070d/InstallMacOSX.dmg)
 OS X 10.11 |  埃尔卡皮坦| [Direct Download](http://updates-http.cdn-apple.com/2019/cert/061-41424-20191024-218af9ec-cf50-4516-9011-228c78eda3d2/InstallMacOSX.dmg)
 macOS 10.12 |  塞拉利昂| [Direct Download](http://updates-http.cdn-apple.com/2019/cert/061-39476-20191023-48f365f4-0015-4c41-9f44-39d3d2aca067/InstallOS.dmg)
 macOS 10.13 |  高塞拉利昂|  不适用
 macOS 10.14 |  莫哈韦沙漠|  不适用
 macOS 10.15 |  卡塔琳娜| [App Store](https://apps.apple.com/de/app/macos-catalina/id1466841314)

### Kernel Extensions

#### Display Status of Loaded Kernel Extensions
```bash
须藤kextstat -l
```

#### Load Kernel Extension
```bash
sudo kextload -b com.apple.driver.ExampleBundle
```

#### Unload Kernel Extensions
```bash
sudo kextunload -b com.apple.driver.ExampleBundle
```

### LaunchAgents

请参阅 [this file](https://github.com/herrbischoff/awesome-macos-command-line/blob/master/launchagents.md).


### LaunchServices

#### Rebuild LaunchServices Database
 为了独立于OS X版本，这依赖于`locate`查找`lsregister`.  如果您尚未建立`locate`数据库， [do it](#build-locate-database).
```bash
须藤$（locate lsregister）-kill -seed -r
```

### Login Window

#### Set Login Window Text
```bash
sudo默认写/Library/Preferences/com.apple.loginwindow LoginwindowText“您的文本”
```

### Memory Management

#### Purge memory cache
```bash
须藤吹扫
```

#### Show Memory Statistics
```bash
## One time
vm_stat

## Table of data, repeat 10 times total, 1 second wait between each poll
vm_stat -c 10 1
```

### Notification Center

#### Notification Center Service
```bash
## Disable
launchctl卸载-w /System/Library/LaunchAgents/com.apple.notificationcenterui.plist &amp;&amp; \
killall -9 NotificationCenter

## Enable (Default)
launchctl load -w /System/Library/LaunchAgents/com.apple.notificationcenterui.plist
```

### QuickLook

#### Preview via QuickLook
```bash
qlmanage -p /路径/到/文件
```

### Remote Apple Events
```bash
## Status
sudo systemsetup -getremoteappleevents

## Enable
sudo systemsetup -setremoteappleevents在

## Disable (Default)
sudo systemsetup -setremoteappleevents关闭
```

### Root User

```bash
## Enable
dsenableroot

## Disable
dsenableroot -d
```

### Safe Mode Boot

```bash
## Status
nvram引导参数

## Enable
sudo nvram boot-args =“-x”

## Disable
sudo nvram boot-args =“”
```

### Save Dialogs
Significantly improve the now rather slow animation in save dialogs.
```bash
默认写入NSGlobalDomain NSWindowResizeTime .001
```

### Screenshots

#### Take Delayed Screenshot
3秒后以JPEG格式截屏，并显示在“预览”中.
```bash
屏幕捕获-T 3 -t jpg -P delaypic.jpg
```

#### Save Screenshots to Given Location
将位置设置为“〜/桌面”.
```bash
默认写com.apple.screencapture位置〜/ Desktop &amp;&amp; \
杀死所有SystemUIServer
```

#### Save Screenshots in Given Format
 将格式设置为“ png”.  其他选项包括`bmp`，`gif`，`jpg`，`jpeg`，`pdf`，`tiff`.
```bash
默认写入com.apple.screencapture类型-string“ png”
```

#### Disable Shadow in Screenshots
```bash
默认写com.apple.screencapture disable-shadow -bool true &amp;&amp; \
杀死所有SystemUIServer
```

#### Set Default Screenshot Name
日期和时间保持不变.
```bash
默认写入com.apple.screencapture名称“示例名称” &amp;&amp; \
杀死所有SystemUIServer
```

### Software Installation

#### Install PKG
```bash
安装程序-pkg /path/to/installer.pkg -target /
```

### Sidecar

#### Use on Incompatible Macs
根据机器的寿命，这可能会或可能不会起作用.
```bash
## Enable
默认写com.apple.sidecar.display AllowAllDevices -bool true &amp;&amp; \
默认写com.apple.sidecar.display hasShownPref -bool true

## Disable (Default)
默认删除com.apple.sidecar.display
```

### Software Update

#### Ignore Specific Software Update
 标识符可以通过`softwareupdate --list`找到.  在下面的示例中，在Mojave上，将忽略对Catalina的所有更新提示，因为后者删除了32位支持.
```bash
sudo / usr / sbin / softwareupdate-忽略“ macOS Catalina”
```

#### Install All Available Software Updates
```bash
sudo软件更新-ia
```

#### Set Software Update Check Interval
设置为每天检查，而不是每周检查.
```bash
默认写com.apple.SoftwareUpdate ScheduleFrequency -int 1
```

#### Show Available Software Updates
```bash
sudo softwareupdate-列表
```

#### Set Software Update Server
 仅应出于测试目的或不受管理的客户端执行此操作.  要在整个网络范围内使用，请正确设置DNS以及 [Apple SUS service](http://krypted.com/mac-security/using-the-software-update-service-on-mountain-lion-server/)  并通过OpenDirectory绑定您的客户.  或者，使用 [Reposado](https://github.com/wdas/reposado) 加上正确的网络DNS设置以使解析透明. [Margarita](https://github.com/jessepeterson/margarita) 看起来也不错.
```bash
## Use own SUS
sudo默认值写入/Library/Preferences/com.apple.SoftwareUpdate CatalogURL http://su.example.com:8088/index.sucatalog

## Reset to Apple SUS
sudo默认值删除/Library/Preferences/com.apple.SoftwareUpdate CatalogURL
```

### Software Version

#### Show System Software Version
```bash
sw_vers -productVersion
```

### Spotlight

#### Spotlight Indexing
```bash
## Disable
mdutil -i off -d / path / to / volume

## Enable (Default)
在/ path / to / volume上的mdutil -i
```

#### Erase Spotlight Index and Rebuild
```bash
mdutil -E /路径/到/卷
```

#### Search via Spotlight
```bash
mdfind -name&#39;searchterm&#39;
```

#### Show Spotlight Indexed Metadata
```bash
mdls /路径/到/文件
```

### System Integrity Protection

#### Disable System Integrity Protection
Reboot while holding <kbd>Cmd</kbd> + <kbd>R</kbd>, open the Terminal application and enter:
```bash
csrutil禁用&amp;&amp;重新启动
```

#### Enable System Integrity Protection
Reboot while holding <kbd>Cmd</kbd> + <kbd>R</kbd>, open the Terminal application and enter:
```bash
csrutil启用&amp;&amp;重新启动
```

### Date and Time

#### List Available Timezones
```bash
sudo systemsetup -listtimezones
```

#### Set Timezone
```bash
sudo systemsetup -settimezone欧洲/柏林
```

#### Set Clock Using Network Time
```bash
## Status
须藤系统设置getusingnetworktime

## Enable (Default)
sudo systemsetup setusingnetworktime on

## Disable
sudo systemsetup setusingnetworktime关闭
```


## Terminal

#### Ring Terminal Bell
敲响终端铃（如果启用）并在其上贴上徽章.
```bash
贝尔
```

### Alternative Terminals

- [Alacritty](https://github.com/jwilm/alacritty) -跨平台，GPU加速的终端仿真器.
- [iTerm2](https://iterm2.com) -更好的Terminal.app.
- [kitty](https://sw.kovidgoyal.net/kitty/) -先进的GPU加速终端仿真器.

### Shells

#### Bash
安装最新版本并设置为当前用户的默认外壳程序：
```bash
brew install bash &amp;&amp; \
 echo $（brew --prefix）/ bin / bash |  sudo tee -a / etc / shells &amp;&amp; \
chsh -s $（brew --prefix）/ bin / bash
```

- [Homepage](https://www.gnu.org/software/bash/) -OS X和大多数其他基于Unix的操作系统的默认外壳.
- [Bash-it](https://github.com/Bash-it/bash-it) -社区Bash框架，例如Bash的Oh My Zsh.

#### fish
安装最新版本并设置为当前用户的默认外壳程序：
```bash
酿造鱼&amp;&amp; \
 echo $（brew --prefix）/ bin / fish |  sudo tee -a / etc / shells &amp;&amp; \
chsh -s $（brew --prefix）/ bin /鱼
```

- [Homepage](http://fishshell.com) -智能且用户友好的命令行
OS X，Linux和其他系列的外壳.
- [The Fishshell Framework](https://github.com/oh-my-fish/oh-my-fish) -提供核心基础结构，使您可以安装扩展或修改外壳外观的软件包.
- [Installation & Configuration Tutorial](https://github.com/ellerbrock/fish-shell-setup-osx) -如何在OS X上使用Fisherman，Powerline字体，iTerm2和Budspencer主题设置鱼壳.

#### Zsh
安装最新版本并设置为当前用户的默认外壳程序：
```bash
brew install zsh &amp;&amp; \
sudo sh -c&#39;echo $（brew --prefix）/ bin / zsh &gt;&gt; / etc / shells&#39;&amp;&amp; \
chsh -s $（brew --prefix）/ bin / zsh
```

- [Homepage](http://www.zsh.org) -Zsh是一种设计用于交互式使用的外壳程序，尽管它也是一种功能强大的脚本语言.
- [Oh My Zsh](http://ohmyz.sh) -用于管理Zsh配置的开源，社区驱动的框架.
- [Prezto](https://github.com/sorin-ionescu/prezto)  -快速的Zsh框架.  通过合理的默认值，别名，函数，自动完成和提示主题来丰富命令行界面环境.
- [zgen](https://github.com/tarjoilija/zgen)  -另一个用于管理zsh配置的开源框架.  Zgen将加载与oh-my-zsh兼容的插件和主题，并具有更快和自动克隆配置中使用的所有插件的优势.

### Terminal Fonts

- [Anonymous Pro](http://www.marksimonson.com/fonts/view/anonymous-pro) -四个固定宽度字体家族，在设计时考虑了编码.
- [Codeface](https://github.com/chrissimpkins/codeface) -供开发人员使用的等距字体的库和存储库.
- [DejaVu Sans Mono](https://dejavu-fonts.github.io/) -基于Vera字体的字体家族.
- [Hack](http://sourcefoundry.org/hack/) -Hack经过手工修饰，并在视觉上保持平衡，可以成为您首选的代码.
- [Inconsolata](http://levien.com/type/myfonts/inconsolata.html) -等宽字体，设计用于代码清单等.
- [Input](http://input.fontbureau.com) -专为代码设计的灵活字体系统.
- [Meslo](https://github.com/andreberg/Meslo-Font) -Apple的Menlo字体的自定义版本.
- [Operator Mono](https://www.typography.com/fonts/operator/overview/) -等宽字体（商业）的一种令人惊讶的可用替代方法.
- [Powerline Fonts](https://github.com/powerline/fonts) -Powerline插件的修补字体回购.
- [Source Code Pro](https://adobe-fonts.github.io/source-code-pro/) -用于用户界面和编码环境的等宽字体系列.


## Glossary

### Mac OS X, OS X, and macOS Version Information

 版本|  代号|  发布日期|  最新版本
-------------------------- | ------------------ | ------------------ | -------------------------------------
 Rhapsody开发人员发布|  Grail1Z4 / Titan1U |  1997年8月31日|  DR2（1998年5月14日）
 Mac OS X服务器1.0 |  赫拉|  1999年3月16日|  1.2v3（2000年10月27日）
 Mac OS X开发人员预览|  不适用  1999年3月16日|  DP4（2000年4月5日）
 Mac OS X公开Beta版|  科迪亚克|  2000年9月13日|  不适用
 Mac OS X 10.0 |  猎豹  2001年3月24日|  10.0.4（2001年6月22日）
 Mac OS X 10.1 |  彪马|  2001年9月25日|  10.1.5（2002年6月6日）
 Mac OS X 10.2 |  美洲虎|  2002年8月24日|  10.2.8（2003年10月3日）
 Mac OS X 10.3 |  豹|  2003年10月24日|  10.3.9（2005年4月15日）
 Mac OS X 10.4 |  老虎|  2005年4月29日|  10.4.11（2007年11月14日）
 Mac OS X 10.5 |  豹纹|  2007年10月26日|  10.5.8（2009年8月5日）
 Mac OS X 10.6 |  雪豹|  2009年8月28日|  10.6.8 v1.1（2011年7月25日）
 Mac OS X 10.7 |  狮子|  2011年7月20日|  10.7.5（2012年9月19日）
 OS X 10.8 |  山狮|  2012年7月25日|  10.8.5（12F45）（2013年10月3日）
 OS X 10.9 |  小牛|  2013年10月22日|  10.9.5（13F1112）（2014年9月18日）
 OS X 10.10 |  优胜美地  2014年10月16日|  10.10.5（14F27）（2015年8月13日）
 OS X 10.11 |  埃尔卡皮坦|  2015年9月30日|  10.11.6（15G31）（2016年7月18日）
 macOS 10.12 |  塞拉利昂|  2016年9月20日|  10.12.6（16G29）（2017年7月19日）
 macOS 10.13 |  高塞拉利昂|  2017年9月25日|  10.13.6（17G65）（2018年7月9日）
 macOS 10.14 |  莫哈韦沙漠|  2018年9月24日|  10.14.6（18G3020）（2020年1月28日）
 macOS 10.15 |  卡塔琳娜|  2019年10月7日|  10.15.3（19D76）（2020年1月28日）


## License

<a rel="license" href="https://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://licensebuttons.net/l/by-sa/4.0/88x31.png" /><br />这项工作是根据<a rel="license" href="https://creativecommons.org/licenses/by-sa/4.0/">知识共享署名-相同方式共享4.0国际许可许可的</a> .
