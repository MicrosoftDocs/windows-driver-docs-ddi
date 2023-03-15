---
UID: NS:winddiui._DOCUMENTPROPERTYHEADER
title: _DOCUMENTPROPERTYHEADER (winddiui.h)
description: The DOCUMENTPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDocumentPropertySheets function.
tech.root: print
ms.date: 03/09/2023
keywords: ["DOCUMENTPROPERTYHEADER structure"]
ms.keywords: "*PDOCUMENTPROPERTYHEADER, DOCUMENTPROPERTYHEADER, DOCUMENTPROPERTYHEADER structure [Print Devices], PDOCUMENTPROPERTYHEADER, PDOCUMENTPROPERTYHEADER structure pointer [Print Devices], _DOCUMENTPROPERTYHEADER, print.documentpropertyheader, print_interface-graphics_d12da62c-2384-4bc3-a83d-ed948460d718.xml, winddiui/DOCUMENTPROPERTYHEADER, winddiui/PDOCUMENTPROPERTYHEADER"
req.header: winddiui.h
req.include-header: Winddiui.h
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
req.typenames: DOCUMENTPROPERTYHEADER, *PDOCUMENTPROPERTYHEADER
f1_keywords:
 - _DOCUMENTPROPERTYHEADER
 - winddiui/_DOCUMENTPROPERTYHEADER
 - PDOCUMENTPROPERTYHEADER
 - winddiui/PDOCUMENTPROPERTYHEADER
 - DOCUMENTPROPERTYHEADER
 - winddiui/DOCUMENTPROPERTYHEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - _DOCUMENTPROPERTYHEADER
 - PDOCUMENTPROPERTYHEADER
 - DOCUMENTPROPERTYHEADER
---

## -description

The DOCUMENTPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function.

## -struct-fields

### -field cbSize

Size, in bytes, of the DOCUMENTPROPERTYHEADER structure.

### -field Reserved

Reserved. Must be zero.

### -field hPrinter

Printer handle.

### -field pszPrinterName

Pointer to a NULL-terminated string representing the printer's name.

### -field pdmIn

Pointer to an input [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure that the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should copy into the printer interface DLL's internal **DEVMODEW** structure (before the property sheet is displayed, if applicable). If DM_IN_BUFFER or DM_MODIFY is not set in **fMode**, this pointer is **NULL**.

### -field pdmOut

Pointer to an output **DEVMODEW** structure into which the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should copy the printer interface DLL's internal **DEVMODEW** contents (after the property sheet has been displayed, if applicable). If DM_OUT_BUFFER or DM_COPY is not set in **fMode**, this pointer is **NULL**.

### -field cbOut

Specifies the size, in bytes, of the buffer to which **pdmOut** points. For more information, see the following Remarks section.

### -field fMode

One or more of the bit flags listed in the following table. (The flags are defined in header files Wingdi.h and Winddiui.h.)

| Flag | Definition |
|---|---|
| No flags set (that is, **fMode** is 0). | The [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should return the size, in bytes, of its DEVMODEW structure, including all public and private members, in the **cbOut** member. |
| DM_ADVANCED | If set, the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should only create the Advanced document page. If not set, the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should create both the PageSetup and Advanced document pages. (See the description of the **pDlgPage** member of the [COMPROPSHEETUI](../compstui/ns-compstui-_compropsheetui.md) structure.) |
| DM_IN_BUFFER or DM_MODIFY | The caller has supplied a DEVMODEW structure pointer in **pdmIn**, and the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should update its internal DEVMODEW structure to reflect the contents of the supplied DEVMODEW. |
| DM_IN_PROMPT or DM_PROMPT | The [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should create its property sheet pages. (This flag is never set if the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function's *pPSUIInfo* parameter is **NULL**.) |
| DM_NOPERMISSION | The printer interface DLL's [\_CPSUICALLBACK](../compstui/nc-compstui-_cpsuicallback.md)-typed callback should not allow the user to modify properties on the displayed property sheet pages. |
| DM_OUT_BUFFER or DM_COPY | The caller has supplied a DEVMODEW structure pointer in **pdmOut**, and the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should copy the contents of its internal DEVMODEW structure into the supplied DEVMODEW. |
| DM_PROMPT_NON_MODAL | The [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function should create its property sheet pages, and launch a non-modal UI. (This flag is never set if the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function's *pPSUIInfo* parameter is **NULL**.) |
| DM_USER_DEFAULT | Not used. |
| DM_OUT_DEFAULT or DM_UPDATE | Not used. |

## -remarks

The input value in the **cbOut** member is not necessarily equal to the size of the buffer pointed to by the **pdmOut** member. For example, when the *pPSUInfo* parameter of the [DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md) function is **NULL**, and if either the **fMode** member of the DOCUMENTPROPERTYHEADER structure is zero, or the **pdmOut** member of the same structure is **NULL**, a driver should write the total size of the printer's [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure (including the public and private structure members) in the **cbOut** member. In such a case, a driver should treat the **cbOut** member as a "write-only" member. Thus, your driver should not use **cbOut** member as the size of the buffer pointed to by the **pdmOut** member if the DrvDocumentPropertySheets function has been called. The "plotter" sample that ships with the Windows Driver Kit (WDK) demonstrates how to use the **cbOut** member correctly.

## -see-also

[**COMPROPSHEETUI**](../compstui/ns-compstui-_compropsheetui.md)

[**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew)

[DrvDocumentPropertySheets](./nf-winddiui-drvdocumentpropertysheets.md)

[MSPLOT Plotter Driver Sample](https://github.com/microsoftarchive/msdn-code-gallery-microsoft/tree/master/Official%20Windows%20Driver%20Kit%20Sample/Windows%20Driver%20Kit%20(WDK)%208.1%20Samples/%5BC%2B%2B%5D-windows-driver-kit-81-cpp/WDK%208.1%20C%2B%2B%20Samples/MSPLOT%20Plotter%20Driver%20Sample/C%2B%2B)