---
UID: NS:compstui._PSPINFO
title: _PSPINFO (compstui.h)
description: The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a DLGPAGE structure.
old-location: print\pspinfo.htm
tech.root: print
ms.assetid: 80a15ee4-e160-49fc-9c61-a14b14d19751
ms.date: 04/20/2018
ms.keywords: "*PPSPINFO, PPSPINFO, PPSPINFO structure pointer [Print Devices], PSPINFO, PSPINFO structure [Print Devices], _PSPINFO, compstui/PPSPINFO, compstui/PSPINFO, cpsuifnc_0e5bb634-1f21-4e4d-aee9-c45ff0dc1c26.xml, print.pspinfo"
ms.topic: struct
f1_keywords:
 - "compstui/PSPINFO"
req.header: compstui.h
req.include-header: Compstui.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- compstui.h
api_name:
- PSPINFO
product:
- Windows
targetos: Windows
req.typenames: PSPINFO, *PPSPINFO
---

# _PSPINFO structure

## -description

The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a [DLGPAGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_dlgpage) structure.

## -struct-fields

### -field cbSize

CPSUI-supplied size, in bytes, of the PSPINFO structure.

### -field wReserved

Reserved.

### -field hComPropSheet

CPSUI-supplied handle to the parent of the page whose handle is contained in **hCPSUIPage**.

### -field hCPSUIPage

CPSUI-supplied handle to the property sheet page.

### -field pfnComPropSheet

CPSUI-supplied pointer to its [ComPropSheet](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/nc-compstui-pfncompropsheet) function.

## -remarks

Before CPSUI calls **CreatePropertySheetPage** to create a property sheet page, it expands the size of the standard PROPSHEETPAGE structure in order to append a PSPINFO structure. When the operating system calls a dialog box procedure (pointed to by a [DLGPAGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_dlgpage) structure) and specifies a WM_INITDIALOG message, the function's **lParam** member points to the expanded PROPSHEETPAGE structure containing the PSPINFO structure.

(The **CreatePropertySheetPage** function, PROPSHEETPAGE structure, WM_INITDIALOG message, and dialog box procedures are all described in the Microsoft Windows SDK documentation.)

To obtain the PSPINFO structure's address, use the PPSPINFO_FROM_WM_INITDIALOG_LPARAM macro (defined in compstui.h) as follows:

```cpp
PPSPINFO pPspInfo;
if (Msg == WM_INITDIALOG) {
    pPspInfo = PPSPINFO_FROM_WM_INITDIALOG_LPARAM(lParam);
}
```

The PSPINFO structure pointer can be saved for later use, but the structure's contents must not be modified.
