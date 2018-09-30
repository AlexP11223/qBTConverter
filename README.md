# qBTConverter
Tool for replacing paths in qBittorent `.fastresume` files.
For example, useful when moving to different PC or OS, especially from Windows to Linux/MacOS because they don't have drive letter paths.

Initially created by grasmanek94 https://qbforums.shiki.hu/index.php?topic=3925.0

You can build it from the source code as described in the next section or download .exe in Releases https://github.com/AlexP11223/qBTConverter/releases

# Building

Can be build using any modern Visual Studio with C#/.NET 4.0, such as VS 2017 Community (free). Probably works on Mono too, but not tested.

Simply open the `.sln` file and Build Solution.

# Usage

Open a command prompt in the folder with the .exe and run: 

    qBTConvert <qBittorent BT_backup dir> <your windows download directory> <your linux download directory>
    
Examples:

    qBTConvert C:\Users\grasmanek94\AppData\Local\qBittorrent\BT_backup V:\downloads /data/torrents/downloads
    qBTConvert C:\Users\grasmanek94\AppData\Local\qBittorrent\BT_backup U:\downloads /data/torrents/downloads
    
You can also add `--verbose` at the end to see list of skipped files.

It does not modify the original files, the results will be in `/out` subfolder of `BT_backup/`.

## Notes for Windows to Linux qBittorent migration

- Re-create all your categories in the Linux qBittorrent client.
- Shutdown qBittorent on all your machines (both Windows and Linux).
- Transfer all torrent DATA FILES and KEEP THE SAME FILE STRUCTURE (from windows to linux).
- Copy all torrent files from `C:\Users\<your user>\AppData\Local\qBittorrent\BT_backup` to `/home/<your linux qbittorrent user>/.local/share/data/qBittorrent/BT_backup`.
- Run this tool as described above and move everything from `C:\Users\<your user>\AppData\Local\qBittorrent\BT_backup\out` to `/home/<your linux qbittorrent user>/.local/share/data/qBittorrent/BT_backup`.
