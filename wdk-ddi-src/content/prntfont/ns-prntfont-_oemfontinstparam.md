---
UID: NS:prntfont._OEMFONTINSTPARAM
title: "_OEMFONTINSTPARAM"
author: windows-driver-content
description: The OEMFONTINSTPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI::FontInstallerDlgProc method.
old-location: print\oemfontinstparam.htm
old-project: print
ms.assetid: cdd3ed28-a077-4b89-9222-ba282b9c7205
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_OEMFONTINSTPARAM, OEMFONTINSTPARAM structure [Print Devices], prntfont/POEMFONTINSTPARAM, prntfont/OEMFONTINSTPARAM, OEMFONTINSTPARAM, print_unidrv-pscript_ui_d306ca78-7f06-4ccf-a501-7470f33f96cb.xml, *POEMFONTINSTPARAM, print.oemfontinstparam, POEMFONTINSTPARAM structure pointer [Print Devices], POEMFONTINSTPARAM"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Printoem.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	prntfont.h
apiname:
-	OEMFONTINSTPARAM
product: Windows
targetos: Windows
req.typenames: OEMFONTINSTPARAM, *POEMFONTINSTPARAM
req.product: Windows 10 or later.
---

# _OEMFONTINSTPARAM structure


## -description


The OEMFONTINSTPARAM structure is used as an input parameter to a user interface plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554176">IPrintOemUI::FontInstallerDlgProc</a> method.


## -syntax


````
typedef struct _OEMFONTINSTPARAM {
  DWORD  cbSize;
  HANDLE hPrinter;
  HANDLE hModule;
  HANDLE hHeap;
  DWORD  dwFlags;
  PWSTR  pFontInstallerName;
} OEMFONTINSTPARAM, *POEMFONTINSTPARAM;
````


## -struct-fields




#### - cbSize

Size, in bytes, of the OEMFONTINSTPARAM structure.


#### - hPrinter

Unidrv-supplied printer handle.


#### - hModule

Unidrv-supplied handle to the user interface plug-in.


#### - hHeap

Unidrv-supplied handle to a heap from which space can be allocated by calling the <b>HeapAlloc</b> function (described in the Microsoft Windows SDK documentation).


#### - dwFlags

Unidrv-supplied flags. The only defined flag is FG_CANCHANGE which, if set, indicates the user interface should allow the user to change the installed fonts. Otherwise the user interface should be displayed in read-only mode.


#### - pFontInstallerName

Pointer to a string representing the font installer's name. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff554176">IPrintOemUI::FontInstallerDlgProc</a> method must supply this string if the received message is WM_USER+WM_FI_NAME. The string must be placed in memory allocated using <b>hHeap</b>.

