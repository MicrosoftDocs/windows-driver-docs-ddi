---
UID: NS:compstui._PSPINFO
title: "_PSPINFO"
author: windows-driver-content
description: The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a DLGPAGE structure.
old-location: print\pspinfo.htm
old-project: print
ms.assetid: 80a15ee4-e160-49fc-9c61-a14b14d19751
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PSPINFO, print.pspinfo, cpsuifnc_0e5bb634-1f21-4e4d-aee9-c45ff0dc1c26.xml, PPSPINFO structure pointer [Print Devices], _PSPINFO, compstui/PSPINFO, PPSPINFO, compstui/PPSPINFO, *PPSPINFO, PSPINFO structure [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	compstui.h
apiname:
-	PSPINFO
product: Windows
targetos: Windows
req.typenames: PSPINFO, *PPSPINFO
---

# _PSPINFO structure


## -description


The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a <a href="..\compstui\ns-compstui-_dlgpage.md">DLGPAGE</a> structure.


## -syntax


````
typedef struct _PSPINFO {
  WORD            cbSize;
  WORD            wReserved;
  HANDLE          hComPropSheet;
  HANDLE          hCPSUIPage;
  PFNCOMPROPSHEET pfnComPropSheet;
} PSPINFO, *PPSPINFO;
````


## -struct-fields




### -field cbSize

CPSUI-supplied size, in bytes, of the PSPINFO structure.


### -field wReserved

Reserved.


### -field hComPropSheet

CPSUI-supplied handle to the parent of the page whose handle is contained in <b>hCPSUIPage</b>.


### -field hCPSUIPage

CPSUI-supplied handle to the property sheet page.


### -field pfnComPropSheet

CPSUI-supplied pointer to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function.


## -remarks


Before CPSUI calls <b>CreatePropertySheetPage</b> to create a property sheet page, it expands the size of the standard PROPSHEETPAGE structure in order to append a PSPINFO structure. When the operating system calls a dialog box procedure (pointed to by a <a href="..\compstui\ns-compstui-_dlgpage.md">DLGPAGE</a> structure) and specifies a WM_INITDIALOG message, the function's <b>lParam</b> member points to the expanded PROPSHEETPAGE structure containing the PSPINFO structure.

(The <b>CreatePropertySheetPage</b> function, PROPSHEETPAGE structure, WM_INITDIALOG message, and dialog box procedures are all described in the Microsoft Windows SDK documentation.)

To obtain the PSPINFO structure's address, use the PPSPINFO_FROM_WM_INITDIALOG_LPARAM macro (defined in compstui.h) as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PPSPINFO pPspInfo;
if (Msg == WM_INITDIALOG) {
    pPspInfo = PPSPINFO_FROM_WM_INITDIALOG_LPARAM(lParam);
}</pre>
</td>
</tr>
</table></span></div>The PSPINFO structure pointer can be saved for later use, but the structure's contents must not be modified.


