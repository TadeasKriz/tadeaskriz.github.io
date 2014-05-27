---
title: Droidium Unit API draft
---

## Shrinkwrap for Android

.aar = AndroidArchive

### Structure

* AndroidManifest.xml (not compiled)
* classes.jar - compiled classes
* R.txt - list of resources
* res/ - not compiled
* assets/

#### R.txt format

```
int {type} {name} {id in hex format}
```

e.g.

```
int string abs__action_bar_home_description 0x7f090000
```

### Usage

AndroidArchive archive = ShrinkWrap.create(AndroidArchive.class);

## APKCreator

