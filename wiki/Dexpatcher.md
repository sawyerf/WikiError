# Dexpatcher-Graddle-Samples

## Aapt2 Error
- [Installation Of Aapt2](https://github.com/DexPatcher/dexpatcher-gradle/issues/24)


## Sdk Version Error
### Error
```
com.android.builder.internal.aapt.v2.Aapt2Exception: Android resource linking failed
/home/alarm/.gradle/caches/transforms-2/files-2.1/373a727e91671bf4203d279143a78819/res/values-v23/styles.xml:8:5-143: AAPT: error: style attribute 'android:attr/windowLightStatusBar' not found.
    
error: resource android:style/TextAppearance.Material.Widget.Button.Borderless.Colored not found.
error: resource android:style/TextAppearance.Material.Widget.Button.Colored not found.
error: resource android:style/TextAppearance.Material.Widget.Button.Inverse not found.
/home/alarm/.gradle/caches/transforms-2/files-2.1/373a727e91671bf4203d279143a78819/res/values-v24/styles.xml:36:5-62:13: AAPT: error: style attribute 'android:attr/contextPopupMenuStyle' not found.
/home/alarm/.gradle/caches/transforms-2/files-2.1/373a727e91671bf4203d279143a78819/res/values-v24/styles.xml:63:5-92:13: AAPT: error: style attribute 'android:attr/contextPopupMenuStyle' not found.
/home/alarm/.gradle/caches/transforms-2/files-2.1/373a727e91671bf4203d279143a78819/res/values-v24/styles.xml:93:5-118:13: AAPT: error: style attribute 'android:attr/contextPopupMenuStyle' not found.
/home/alarm/.gradle/caches/transforms-2/files-2.1/373a727e91671bf4203d279143a78819/res/values-v24/styles.xml:126:5-129:13: AAPT: error: style attribute 'android:attr/contextPopupMenuStyle' not found.
```
### Solution
- Change version of Sdk in `build.gradle`
