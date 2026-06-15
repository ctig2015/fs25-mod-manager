# FS25 Mod Manager - Setup Guide

## Quick Start (5 minutes)

### Step 1: Install Python

1. Download Python 3.11 from [python.org](https://www.python.org/downloads/)
2. During installation, **CHECK** the box that says "Add Python to PATH"
3. Click "Install Now"
4. Wait for installation to complete

### Step 2: Download the App

Option A - Using Git (Recommended):
```bash
git clone https://github.com/ctig2015/fs25-mod-manager.git
cd fs25-mod-manager
```

Option B - Download as ZIP:
1. Go to https://github.com/ctig2015/fs25-mod-manager
2. Click "Code" → "Download ZIP"
3. Extract the ZIP file to a folder like `C:\FS25ModManager`

### Step 3: Install Dependencies

1. Open Command Prompt (Win+R, type `cmd`, press Enter)
2. Navigate to the app folder:
   ```bash
   cd path\to\fs25-mod-manager
   ```
3. Run:
   ```bash
   pip install -r requirements.txt
   ```

### Step 4: Run the App

```bash
python main.py
```

The application window should open!

---

## First Use

### Finding Your FS25 Mods Folder

Farming Simulator 25 stores mods in one of these locations:

**Standard Location:**
```
C:\Users\[YourUsername]\AppData\Roaming\Farming Simulator 2025\mods
```

**Alternative Locations:**
- Steam Installation: `C:\Program Files\steamapps\common\Farming Simulator 25\mods`
- Custom Installation: Check your FS25 game settings

### Locating Your Mods

1. Press `Win+R` to open Run dialog
2. Type: `%appdata%\Farming Simulator 2025\mods` and press Enter
3. This opens your mods folder in Windows Explorer
4. Copy the full path from the address bar

### Loading Mods in the App

1. Click "Browse Mods Folder" in the app
2. Paste the path you copied (or navigate to it)
3. Click "Select Folder"
4. Wait for the app to scan all `.zip` files
5. Your mods will appear in the list!

---

## Features Explained

### Drag and Drop Reordering

The mod load order matters in FS25. Mods loaded first can be overridden by mods loaded later.

- Click and drag a mod up or down to change load order
- The order is automatically saved

### Enable/Disable Mods

- **Checked** = Mod is active
- **Unchecked** = Mod is disabled (won't load in FS25)
- Change state by clicking the checkbox
- Use "Enable All" / "Disable All" buttons for quick actions

### Filtering by Type

The app auto-detects mod types:
- **Tractor** - Tractor script mods
- **Script** - General script mods
- **Map** - Map and terrain mods
- **Crop** - Crop and plant mods
- **Vehicle** - Vehicle mods

Use the filter dropdown to show only certain types.

### Search

Type in the search box to find mods by name instantly. Works together with the type filter.

### Mod Details

Click any mod to see its metadata on the right panel:
- **Name** - Mod name
- **Type** - Auto-detected type
- **Author** - Who created it
- **Version** - Mod version
- **Description** - What the mod does

---

## Troubleshooting

### "Python not found" error

**Solution:** Python wasn't added to PATH during installation.

1. Uninstall Python (Control Panel → Programs)
2. Reinstall Python and CHECK "Add Python to PATH"
3. Restart Command Prompt
4. Try again: `python main.py`

### "No module named 'PyQt6'"

**Solution:** Dependencies weren't installed properly.

```bash
pip install --upgrade pip
pip install -r requirements.txt --force-reinstall
python main.py
```

### App window is blank or won't display

**Solution:** 
1. Close the app
2. Delete the config file at: `C:\Users\[YourUsername]\.fs25_mod_manager\config.json`
3. Rerun: `python main.py`

### Mods not showing up

**Checklist:**
- Are the files `.zip` format? (not `.rar`, `.7z`, etc.)
- Do they contain a `modDesc.xml` file?
- Is the folder path correct?

**Debug:** Open Command Prompt in the mods folder and check the files:
```bash
dir *.zip
```

If no `.zip` files appear, that's the problem!

### FS25 doesn't recognize my mod order

**Note:** FS25 has its own mod manager that may override this app's order. 

**Solution:**
1. In FS25 main menu → Options → Mod Manager
2. Compare the order here with the app
3. If different, FS25's mod manager has priority
4. You may need to set load order in FS25's mod manager instead

---

## Creating a Shortcut

To launch the app without opening Command Prompt:

1. Right-click on your desktop
2. Click "New" → "Shortcut"
3. Paste this path (modify to match your setup):
   ```
   C:\Python311\python.exe C:\path\to\fs25-mod-manager\main.py
   ```
4. Click "Next"
5. Name it "FS25 Mod Manager"
6. Click "Finish"

Now double-click the shortcut to launch!

---

## Advanced: Creating an Executable

Want to distribute the app as a single `.exe` file?

1. Install PyInstaller:
   ```bash
   pip install pyinstaller
   ```

2. Create executable:
   ```bash
   pyinstaller --onefile --windowed main.py
   ```

3. Find it in: `dist\main.exe`

4. Share `main.exe` with others (they don't need Python installed!)

---

## Support & Updates

- **Issues?** Open an issue on [GitHub](https://github.com/ctig2015/fs25-mod-manager/issues)
- **Updates?** Run `git pull` in the folder to get the latest version
- **Questions?** Check the README.md for more info

---

Happy farming! 🚜
