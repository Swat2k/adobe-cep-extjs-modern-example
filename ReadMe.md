### Extension Folders

CEP supports 3 types of extension folders.

 - Product extension folder. Here is a suggestion, but each point product can decide where this folder should be. Third party extension can't be installed at this location.
 
 
	 - ${PP}/CEP/extensions (PPs may use different folder.)


 - System extension folder
	 - Win(x64): `C:\Program Files (x86)\Common Files\Adobe\CEP\extensions`, and `C:\Program Files\Common Files\Adobe\CEP\extensions` (since CEP 6.1)
	 - macOS: `/Library/Application Support/Adobe/CEP/extensions`


 - Per-user extension folder 
	 - Win: `C:\Users\<USERNAME>\AppData\Roaming\Adobe\CEP/extensions`
	 - macOS: `~/Library/Application Support/Adobe/CEP/extensions`

### Debugging Unsigned Extensions

If you are in the midst of development and are not using HTML Extension Builder for debug workflows and want to bypass the need to sign your extensions, you can bypass the check for extension signatures by editing the CSXS preference properties file, located at:

 - Win: regedit > HKEY_CURRENT_USER/Software/Adobe/CSXS.10, then add a new entry PlayerDebugMode of type "string" with the value of "1".
 - macOS: In the terminal, type: `defaults write com.adobe.CSXS.10 PlayerDebugMode 1` (The plist is also located at /Users/`<username>`/Library/Preferences/com.adobe.CSXS.10.plist)


These entries will enable debug extensions to be displayed in the host applications. Please note that, CSXS.10 is given with the assumption that, you are developing the extension for CEP 10. If you are developing extension for previous version of CEP, replace 10 with corresponding version number.