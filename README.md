# Momentum-Apps
Bundle of external apps tweaked for [Momentum Firmware](https://github.com/NextFlip/Momentum-Firmware).

> [!IMPORTANT]
> These apps are already included with all Momentum Firmware releases.
> This repository serves only as a way to keep them updated and maintained easier.

### Why?
Many apps included in Momentum are modified (some lots more than others). This includes:
- Removing/tweaking icons and/or their usages to **support our Asset Packs system**
- Removing duplicate keyboard implementations to **use our extended system keyboard**
- With our system keyboard also **support our CLI command `input keyboard`** to type with PC keyboard
- **Moving location of save files** to a more appropriate location or changing how they are saved
- **Changing application display names** to fit our naming scheme
- **Changing how some menus work/look** or adding **new exclusive menus and features**
- **Improving or extending functionality** and better integrating with the firmware
- **Updating and fixing apps** that were abandoned by the original developers

### How?
**Apps made by the our team are developed right here, the latest versions will always originate from this repository.**

**For all other apps we use git subtrees to pull updates from the creator's repository / other sources such as [@xMasterX's pack](https://github.com/xMasterX/all-the-plugins), while also keeping our own tweaks and additions.**

We didn't want to have fork repos for each single app since it would get out of hand very quick. Instead, we opted for subtrees.

Subtrees work in a very peculiar way: they pull and compare commit history from a remote repo and apply it to a subdirectory of this repo.
That's why the commit history for this repo is so huge, it contains all the commits for all the apps, plus our edits.

To make updating more manageable, we have added some scripts on top of subtrees:
- add a new app with `.utils/add-subtree.sh <path> <repo url> <branch> [subdir]`, this will pull the history and create `path/.gitsubtree` to remember the url, branch and subdir
- run `.utils/update-subtree.sh <path>` to pull updates for a subtree
- or run `.utils/bulk-update-subtrees.sh` to do it for all subtrees
