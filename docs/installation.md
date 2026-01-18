# How to Install

## Supported Blender versions
- Blender 4.5+
- Other versions remain unconfirmed. Since it's a basic modifier-based system, it might work on earlier versions, but not guaranteed.

---

## Installation Procedure

### Step 1: Download the Add-on
Download the SDFusion add-on ZIP files from [Superhive Market](https://superhivemarket.com/products/sdfusion/?ref=1435) or other sources.

![Download Files](images/スクリーンショット 2025-09-27 182625.png)

You will receive:
- **Main add-on file**: `SDFusion_x_x_x.zip` (core add-on)
- **Asset file**: `Cutter_asset_x_x_x.zip` (optional, for additional cutters)

*The numbers in the filenames indicate the version, so they may differ from those shown in this image.*

### Step 2: Install the Add-on
1. Open Blender
2. Go to **Edit > Preferences > Add-ons**
3. Click **Install...** button
4. Select the SDFusion ZIP file and click **Install Add-on**
5. Enable the "SDFusion" add-on by checking the checkbox

---

## Installing Asset Files (v1.7.0+)

SDFusion v1.7.0 and later includes a built-in **Asset Installer** for easy setup.

### Using the Asset Installer (Recommended)

1. Go to **Edit > Preferences > Add-ons**
2. Find and expand **SDFusion**
3. You will see the Asset Library configuration panel

![Preferences Panel](images/6 ページ.png)

#### For New Installation:
If no assets are configured yet, you'll see "Status: Not Configured".

1. Click **"Install Assets..."** button
2. In the dialog:
   - **Asset ZIP File**: Select your `Cutter_asset_x_x_x.zip` file
   - **Install Location**: Choose a folder (default: `Documents/Blender Assets`)
3. Click **OK** to install

![Installation Dialog](images/スクリーンショット 2025-09-27 212159.png)

The installer will:
- Extract the ZIP file to the selected location
- Automatically register it as a Blender Asset Library
- Name the library "SDFusion Assets"

#### For Update/Reinstall:
If assets are already configured, you'll see "Status: Configured Successfully" with the current location.

1. Click **"Update / Reinstall Assets..."** button
2. Select the new ZIP file
3. Confirm to replace existing assets

> **Warning**: Updating will overwrite all existing assets in the library.

---

### Manual Installation (Alternative)

If you prefer manual setup:

1. Extract the asset ZIP file to a folder of your choice
2. Go to **Edit > Preferences > File Paths > Asset Libraries**
3. Click **+** to add a new library
4. Navigate to the extracted folder
5. Name it "SDFusion Assets" (or any name you prefer)

---

## Verify Installation

1. Open Blender's **Asset Browser**
2. Select "SDFusion Assets" from the library dropdown
3. You should see all the cutter objects and node groups

![Asset Browser](images/スクリーンショット 2025-09-27 212938.png)

---

## Access SDFusion

After installation:
1. Open a 3D Viewport
2. Press **N** key to open the sidebar
3. Find the **SDFusion** tab

You're now ready to start using SDFusion!

<span style="font-size: 20px;">Next : [How to Use](how_to_use.md)</span>