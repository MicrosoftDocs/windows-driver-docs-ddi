---
UID: NC:wdbgexts.PWINDBG_EXTENSION_DLL_INIT
title: PWINDBG_EXTENSION_DLL_INIT (wdbgexts.h)
description: The PWINDBG_EXTENSION_DLL_INIT ( WinDbgExtensionDllInit) callback function is used to load and initialize the extension module.
old-location: debugger\windbgextensiondllinit.htm
tech.root: debugger
ms.assetid: 1c97ac8c-9b40-44e8-b669-6b7d4ee2d671
ms.date: 05/03/2018
keywords: ["PWINDBG_EXTENSION_DLL_INIT callback function"]
ms.keywords: PWINDBG_EXTENSION_DLL_INIT, PWINDBG_EXTENSION_DLL_INIT callback, WdbgExts_Callbacks_18383848-27f2-4d4e-a5b0-c6ce27377687.xml, WinDbgExtensionDllInit, WinDbgExtensionDllInit callback function [Windows Debugging], debugger.windbgextensiondllinit, wdbgexts/WinDbgExtensionDllInit
req.header: wdbgexts.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PWINDBG_EXTENSION_DLL_INIT
 - wdbgexts/PWINDBG_EXTENSION_DLL_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdbgexts.h
api_name:
 - WinDbgExtensionDllInit
---

# PWINDBG_EXTENSION_DLL_INIT callback function


## -description

The <b>PWINDBG_EXTENSION_DLL_INIT</b> (<b> WinDbgExtensionDllInit</b>) callback function is used to load and initialize the extension module.

## -parameters

### -param lpExtensionApis

A pointer to a WINDBG_EXTENSION_APIS64 structure, which contains  pointers to functions that you can use for standard operations. Copy the entire structure to a global variable in your DLL. For example, you could create a  global variable named ExtensionApis as shown in the following example.


```cpp
WINDBG_EXTENSION_APIS64   ExtensionApis;
```


### -param MajorVersion

Specifies the Microsoft Windows build type. A value of 0xC indicates the checked build of Windows. A value of 0xF indicates the free build of Windows.   Save this value in a global variable in your DLL. For example, you could create a global variable named SavedMajorVersion.

### -param MinorVersion

Specifies the Windows build number (for example 2600) of the target system. Save this value in a global variable in your DLL. For example, you could create a global variable named SavedMinorVersion.

## -remarks

<i>WinDbgExtensionDllInit</i> is called by the debugger when the extension DLL is loaded.

It is recommended that you always use 64-bit pointers in your code, since the debugger will automatically resize these pointers when necessary. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details. However, if you choose to use 32-bit pointers, the first parameter of <i>WinDbgExtensionDllInit</i> will have the type PWINDBG_EXTENSION_APIS instead of PWINDBG_EXTENSION_APIS64.

For more details, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-wdbgexts-extension-callbacks">Using WdbgExts Extension Callbacks</a>.

