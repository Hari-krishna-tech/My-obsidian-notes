To add a logo (app icon) to your Android app in Android Studio, follow these steps:

  

**1. Prepare Your Logo Image**

• The logo should ideally be in .png format.

• Recommended size is **512x512 pixels** for the best quality across all devices.

**2. Use Image Asset Studio in Android Studio**

1. **Right-click** on the res folder in your project.

2. Go to **New > Image Asset**.

3. In the opened dialog:

• **Icon Type**: Select **Launcher Icons (Adaptive and Legacy)**.

• **Path**: Click **Path** to select your logo image.

• Adjust padding and scaling as necessary.

4. Click **Next**, then **Finish**.

**3. Manually Replace Icons (Optional)**

  

If you want to manually replace the icons, go to:

• **res > mipmap** folders (mipmap-mdpi, mipmap-hdpi, mipmap-xhdpi, mipmap-xxhdpi, mipmap-xxxhdpi).

• Replace the ic_launcher.png files with your logo in each folder for different screen densities.

**4. Update AndroidManifest.xml**

• Ensure the AndroidManifest.xml file is pointing to your new icon:

```
<application
    android:icon="@mipmap/ic_launcher"
    android:roundIcon="@mipmap/ic_launcher_round"
    android:label="@string/app_name"
    ...>
```

**5. Clean and Rebuild the Project**

• Go to **Build > Clean Project** and then **Rebuild Project** to see your new logo in action.

Tag: [[android]]
