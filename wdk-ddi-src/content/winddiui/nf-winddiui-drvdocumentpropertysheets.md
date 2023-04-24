---
UID: NF:winddiui.DrvDocumentPropertySheets
title: DrvDocumentPropertySheets function (winddiui.h)
description: A printer interface DLL's DrvDocumentPropertySheets function is responsible for creating property sheet pages that describe a print document's properties.
tech.root: print
ms.date: 03/09/2023
keywords: ["DrvDocumentPropertySheets function"]
ms.keywords: DrvDocumentPropertySheets, DrvDocumentPropertySheets function [Print Devices], print.drvdocumentpropertysheets, print_interface-graphics_00cc0beb-e6f1-41dd-ae0b-fd59a6d14465.xml, winddiui/DrvDocumentPropertySheets
req.header: winddiui.h
req.include-header: Winddiui.h
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
 - DrvDocumentPropertySheets
 - winddiui/DrvDocumentPropertySheets
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvDocumentPropertySheets
---

## -description

A printer interface DLL's **DrvDocumentPropertySheets** function is responsible for creating property sheet pages that describe a print document's properties.

## -parameters

### -param pPSUIInfo [in, optional]

Caller-supplied pointer to a [**PROPSHEETUI_INFO**](../compstui/ns-compstui-_propsheetui_info.md) structure. Can be **NULL** (see the following Remarks section).

### -param lParam

Caller-supplied integer value that is dependent on the contents of the **Reason** member of the PROPSHEETUI_INFO structure, as listed in the following table.

| Reason value | Definition of *lParam* |
|---|---|
| PROPSHEETUI_REASON_INIT | Pointer to a [**DOCUMENTPROPERTYHEADER**](./ns-winddiui-_documentpropertyheader.md) structure. |
| All other reason values | See the description of the *lParam* parameter for the [PFNPROPSHEETUI](../compstui/nc-compstui-pfnpropsheetui.md) function type. (The [**DOCUMENTPROPERTYHEADER**](./ns-winddiui-_documentpropertyheader.md) structure's address is contained in the **lParamInit** member of the [**PROPSHEETUI_INFO**](../compstui/ns-compstui-_propsheetui_info.md) structure.) |

## -returns

If *pPSUIInfo* is **NULL**, and if either *lParam* -> **fMode** is zero or *lParam -*> **pdmOut** is **NULL**, this function should return the size, in bytes, of the printer's [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. Otherwise, the function's return value is the same as that described in the ReturnValue section of the [PFNPROPSHEETUI](../compstui/nc-compstui-pfnpropsheetui.md) function type. For more information, see the Remarks section.

## -remarks

All [printer interface DLLs](/windows-hardware/drivers/print/printer-interface-dll) must provide a **DrvDocumentPropertySheets** function, which is defined using the [PFNPROPSHEETUI](../compstui/nc-compstui-pfnpropsheetui.md) function type. The function's purpose is to call the [ComPropSheet](../compstui/nc-compstui-pfncompropsheet.md) function, provided by [CPSUI](/windows-hardware/drivers/print/common-property-sheet-user-interface), to specify property sheet pages containing user-modifiable properties for print documents.

If the value received for the *pPSUIInfo* parameter is not **NULL**, the NT-based operating system print spooler is calling the function indirectly, through CPSUI. The following rules apply:

- The function should perform operations as described for the [PFNPROPSHEETUI](../compstui/nc-compstui-pfnpropsheetui.md) function type.

- Flags in the **fMode** member of the [**DOCUMENTPROPERTYHEADER**](./ns-winddiui-_documentpropertyheader.md) structure indicate which property sheet pages to display and whether the user should be allowed to modify a document's properties. The only flags that might be set are DM_IN_PROMPT (or DM_PROMPT), DM_ADVANCED, DM_NOPERMISSION, and DM_OUT_BUFFER (or DM_COPY).

If the value received for the *pPSUIInfo* parameter is **NULL**, the print spooler is calling the function directly, without going through CPSUI. In this case, the *lParam* parameter contains the address of a DOCUMENTPROPERTYHEADER structure, and the following rules apply:

- If the **fMode** member of the [**DOCUMENTPROPERTYHEADER**](./ns-winddiui-_documentpropertyheader.md) structure is zero, or if the **pdmOut** member of the same structure is **NULL**, the function should return just the total size of the printer's [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure, including public and private structure members, in the DOCUMENTPROPERTYHEADER structure's **cbOut** member.

- If the **fMode** member of the DOCUMENTPROPERTYHEADER structure is not zero, the function should perform the operations indicated by the **fMode** flags. The only flags that might be set are DM_IN_BUFFER (or DM_MODIFY), and DM_OUT_BUFFER (or DM_COPY).

## -see-also

[**DOCUMENTPROPERTYHEADER**](./ns-winddiui-_documentpropertyheader.md)

[DrvDevicePropertySheets](./nf-winddiui-drvdevicepropertysheets.md)

[IPrintOemUI::DocumentPropertySheets](../prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets.md)