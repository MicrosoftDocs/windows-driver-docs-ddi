---
UID: NS:compstui._PROPSHEETUI_INFO
title: PROPSHEETUI_INFO (compstui.h)
description: The PROPSHEETUI_INFO structure is used as an input parameter to PFNPROPSHEETUI-typed functions.
tech.root: print
ms.date: 11/16/2022
keywords: ["PROPSHEETUI_INFO structure"]
ms.keywords: "*PPROPSHEETUI_INFO, PPROPSHEETUI_INFO, PPROPSHEETUI_INFO structure pointer [Print Devices], PROPSHEETUI_INFO, PROPSHEETUI_INFO structure [Print Devices], _PROPSHEETUI_INFO, compstui/PPROPSHEETUI_INFO, compstui/PROPSHEETUI_INFO, cpsuifnc_0afe9ac8-ca1f-4984-acc5-04a8955b4b30.xml, print.propsheetui_info"
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
req.typenames: PROPSHEETUI_INFO, *PPROPSHEETUI_INFO
f1_keywords:
 - _PROPSHEETUI_INFO
 - compstui/_PROPSHEETUI_INFO
 - PPROPSHEETUI_INFO
 - compstui/PPROPSHEETUI_INFO
 - PROPSHEETUI_INFO
 - compstui/PROPSHEETUI_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _PROPSHEETUI_INFO
 - PPROPSHEETUI_INFO
 - PROPSHEETUI_INFO
---

## -description

The **PROPSHEETUI_INFO** structure is used as an input parameter to [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui)-typed functions.

## -struct-fields

### -field cbSize

CPSUI-supplied size, in bytes, of the **PROPSHEETUI_INFO** structure.

### -field Version

CPSUI-supplied version number of the **PROPSHEETUI_INFO** structure. The current version number is defined by PROPSHEETUI_INFO_VERSION in compstui.h.

### -field Flags

CPSUI-supplied bit flags. The following flag is defined:

| Flag | Description |
|---|---|
| PSUIINFO_UNICODE | If set, the calling application uses Unicode characters. |

### -field Reason

CPSUI-supplied constant specifying the action to be performed on the property sheet by the [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui)-typed function to which the PROPSHEETUI_INFO structure was passed. One of the following constants will be supplied:

- PROPSHEETUI_REASON_DESTROY

- PROPSHEETUI_REASON_GET_ICON

- PROPSHEETUI_REASON_GET_INFO_HEADER

- PROPSHEETUI_REASON_INIT

- PROPSHEETUI_REASON_SET_RESULT

For information about the meaning of each constant, see the Remarks section of the [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) description.

### -field hComPropSheet

CPSUI-supplied handle to a property sheet [group parent](/windows-hardware/drivers/print/group-parent). This handle can be passed to CPSUI's [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function.

### -field pfnComPropSheet

Address of CPSUI's [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function.

### -field lParamInit

Value received as the *lParam* parameter for the associated PFNPROPSHEETUI-typed function, when the function was first called with a **Reason** of PROPSHEETUI_REASON_INIT. For information about what this value can be, see the description of [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui).

This value is supplied by CPSUI, and is valid for all **Reason** values.

### -field UserData

Optional, private value or pointer supplied by the associated [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui)-typed function, initially set to zero by CPSUI. If the function stores a value in **UserData**, then for subsequent calls to the function, the stored value or pointer is unchanged unless changed by the function.

### -field Result

Result value supplied by the associated [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui)-typed function, initially set to zero by CPSUI. If the function stores a result value in **Result**, then for subsequent calls to the function, the stored value is unchanged unless changed by the function.

If the PFNPROPSHEETUI-typed function's address was specified as an argument to [CommonPropertySheetUI](/windows-hardware/drivers/ddi/compstui/nf-compstui-commonpropertysheetuia), the last value stored in **Result** is returned to **CommonPropertySheetUI** in the location pointed to by its *pResult* argument.
