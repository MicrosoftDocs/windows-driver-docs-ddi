---
UID: NS:compstui._PROPSHEETUI_INFO_HEADER
title: PROPSHEETUI_INFO_HEADER (compstui.h)
description: The PROPSHEETUI_INFO_HEADER structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_INFO_HEADER.
tech.root: print
ms.date: 11/16/2022
keywords: ["PROPSHEETUI_INFO_HEADER structure"]
ms.keywords: "*PPROPSHEETUI_INFO_HEADER, PPROPSHEETUI_INFO_HEADER, PPROPSHEETUI_INFO_HEADER structure pointer [Print Devices], PROPSHEETUI_INFO_HEADER, PROPSHEETUI_INFO_HEADER structure [Print Devices], _PROPSHEETUI_INFO_HEADER, compstui/PPROPSHEETUI_INFO_HEADER, compstui/PROPSHEETUI_INFO_HEADER, cpsuifnc_21dad179-56e1-478c-8a62-628262ca59a8.xml, print.propsheetui_info_header"
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
targetos: Windows
req.typenames: PROPSHEETUI_INFO_HEADER, *PPROPSHEETUI_INFO_HEADER
f1_keywords:
 - _PROPSHEETUI_INFO_HEADER
 - compstui/_PROPSHEETUI_INFO_HEADER
 - PPROPSHEETUI_INFO_HEADER
 - compstui/PPROPSHEETUI_INFO_HEADER
 - PROPSHEETUI_INFO_HEADER
 - compstui/PROPSHEETUI_INFO_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _PROPSHEETUI_INFO_HEADER
 - PPROPSHEETUI_INFO_HEADER
 - PROPSHEETUI_INFO_HEADER
---

## -description

The **PROPSHEETUI_INFO_HEADER** structure is used as an input parameter to an application's [PFNPROPSHEETUI](./nc-compstui-pfnpropsheetui.md)-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_INFO_HEADER.

## -struct-fields

### -field cbSize

CPSUI-supplied size, in bytes, of the **PROPSHEETUI_INFO_HEADER** structure.

### -field Flags

Optional, application-specified bit flags that modify the property sheet page's appearance. The flags listed in the following table can be used in any combination.

| Flag | Description |
|---|---|
| PSUIHDRF_DEFTITLE | If set, CPSUI should include "Default" in the title bar string. CPSUI adds "Default" after the **pTitle** string and, if PSUIHDRF_PROPTITLE is set, before "Properties". |
| PSUIHDRF_EXACT_PTITLE | If set, CPSUI uses the text specified by **pTitle** without modification. This flag overrides PSUIHDRF_DEFTITLE and PSUIHDRF_PROPTITLE. |
| PSUIHDRF_NOAPPLYNOW | If set, CPSUI should not include an **Apply Now** button. |
| PSUIHDRF_PROPTITLE | If set, CPSUI should append "Properties" to the title bar string. (By default, CPSUI sets this flag before calling the application.) |
| PSUIHDRF_USEHICON | If set, the **hIcon**/**IconID** union contains an icon handle. If not set, the union contains an icon resource identifier. |

### -field pTitle

String identifier, representing text to be displayed in the property sheet's title bar. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero. For printer interface DLLs, the string typically contains the printer's name.

### -field hWndParent

Handle to the window to be used as the parent of the property sheet. By default, CPSUI supplies the window handle that it received for the *hWndOwner* parameter to [CommonPropertySheetUI](./nf-compstui-commonpropertysheetuia.md), but the application can overwrite that handle with another.

### -field hInst

Application-supplied instance handle, which CPSUI uses when loading application resources.

### -field DUMMYUNIONNAME

This union identifies the icon to be displayed in the property sheet's title bar.

### -field DUMMYUNIONNAME.hIcon

Defines the **HICON** member **hIcon**.

### -field DUMMYUNIONNAME.IconID

Defines the **ULONG_PTR** member **IconID**. The union member is selected by PSUIHDRF_USEICON in **Flags**.