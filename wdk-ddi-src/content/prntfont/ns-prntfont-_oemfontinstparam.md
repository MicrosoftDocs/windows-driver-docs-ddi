---
UID: NS:prntfont._OEMFONTINSTPARAM
title: _OEMFONTINSTPARAM (prntfont.h)
description: The OEMFONTINSTPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI::FontInstallerDlgProc method.
old-location: print\oemfontinstparam.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["OEMFONTINSTPARAM structure"]
ms.keywords: "*POEMFONTINSTPARAM, OEMFONTINSTPARAM, OEMFONTINSTPARAM structure [Print Devices], POEMFONTINSTPARAM, POEMFONTINSTPARAM structure pointer [Print Devices], _OEMFONTINSTPARAM, print.oemfontinstparam, print_unidrv-pscript_ui_d306ca78-7f06-4ccf-a501-7470f33f96cb.xml, prntfont/OEMFONTINSTPARAM, prntfont/POEMFONTINSTPARAM"
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
targetos: Windows
req.typenames: OEMFONTINSTPARAM, *POEMFONTINSTPARAM
f1_keywords:
 - _OEMFONTINSTPARAM
 - prntfont/_OEMFONTINSTPARAM
 - POEMFONTINSTPARAM
 - prntfont/POEMFONTINSTPARAM
 - OEMFONTINSTPARAM
 - prntfont/OEMFONTINSTPARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - OEMFONTINSTPARAM
---

# _OEMFONTINSTPARAM structure


## -description

The OEMFONTINSTPARAM structure is used as an input parameter to a user interface plug-in's <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-fontinstallerdlgproc">IPrintOemUI::FontInstallerDlgProc</a> method.

## -struct-fields

### -field cbSize

Size, in bytes, of the OEMFONTINSTPARAM structure.

### -field hPrinter

Unidrv-supplied printer handle.

### -field hModule

Unidrv-supplied handle to the user interface plug-in.

### -field hHeap

Unidrv-supplied handle to a heap from which space can be allocated by calling the <b>HeapAlloc</b> function (described in the Microsoft Windows SDK documentation).

### -field dwFlags

Unidrv-supplied flags. The only defined flag is FG_CANCHANGE which, if set, indicates the user interface should allow the user to change the installed fonts. Otherwise the user interface should be displayed in read-only mode.

### -field pFontInstallerName

Pointer to a string representing the font installer's name. The <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-fontinstallerdlgproc">IPrintOemUI::FontInstallerDlgProc</a> method must supply this string if the received message is WM_USER+WM_FI_NAME. The string must be placed in memory allocated using <b>hHeap</b>.
