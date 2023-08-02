# DEPRECATED

Now included in my [JetBrains Collection](https://github.com/diademiemi/ansible_collection_diademiemi.jetbrains)

# Ansible Role Android Studio
This is an Ansible role that installs Android Studio on Linux. It uses the tarball from the official website so this role is not dependent on any package manager.  
It can take a list of plugin IDs which it will automatically install.  

Tested on Fedora 36 with Android Studio 2021.3, should work on any Linux distribution that the Android Studio tarball supports.  

## Requirements

### Base requirements
None  

### Installing plugins
Plugins are installer per-user, so you will need to give `android_studio_user`, this defaults to `{{ ansible_user_id }}`.  

## Variables
| Variable | Default | Description |
|----------|---------|-------------|
| `android_studio_version` | `2021.3.1.17` | Default version of Android Studio to download |
| `android_studio_url` | See [defaults/main.yml](./defaults/main.yml) | Base URL for the Android Studio tarball |
| `android_studio_user` | `{{ ansible_user_id }}` | User to install plugins for. |

## Installing plugins
To install plugins for Android Studio, define the `android_studio_plugins` variable.  
```yaml
android_studio_plugins:
  - 10233 # Discord Integration
  - 17718 # GitHub Copilot
```

You can get this ID by going to the plugin homepage from Android Studio's Plugins tab and copying the number from the URL it opens.  
