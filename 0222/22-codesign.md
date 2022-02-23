# Self signed certificates for MacOS Applications

When you try to open an application on Mac and you get the error, `You do not have permission to open the application xyz` 

You can try self signing the certificate if you trust the application by running the following

`codesign --force --deep --sign - /Applications/AppName.app`