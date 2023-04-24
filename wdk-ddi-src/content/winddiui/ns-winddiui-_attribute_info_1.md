---
UID: NS:winddiui._ATTRIBUTE_INFO_1
title: _ATTRIBUTE_INFO_1 (winddiui.h)
description: The ATTRIBUTE_INFO_1 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied.
tech.root: print
ms.date: 03/09/2023
keywords: ["ATTRIBUTE_INFO_1 structure"]
ms.keywords: "*PATTRIBUTE_INFO_1, ATTRIBUTE_INFO_1, ATTRIBUTE_INFO_1 structure [Print Devices], PATTRIBUTE_INFO_1, PATTRIBUTE_INFO_1 structure pointer [Print Devices], _ATTRIBUTE_INFO_1, print.attribute_info_1, print_interface-graphics_6c838297-1acb-4d8f-aa5d-beab06a6d3d2.xml, winddiui/ATTRIBUTE_INFO_1, winddiui/PATTRIBUTE_INFO_1"
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
req.typenames: ATTRIBUTE_INFO_1, *PATTRIBUTE_INFO_1
f1_keywords:
 - _ATTRIBUTE_INFO_1
 - winddiui/_ATTRIBUTE_INFO_1
 - PATTRIBUTE_INFO_1
 - winddiui/PATTRIBUTE_INFO_1
 - ATTRIBUTE_INFO_1
 - winddiui/ATTRIBUTE_INFO_1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - _ATTRIBUTE_INFO_1
 - PATTRIBUTE_INFO_1
 - ATTRIBUTE_INFO_1
---

## -description

The ATTRIBUTE_INFO_1 structure is used as a parameter for a printer interface DLL's [DrvQueryJobAttributes](./nf-winddiui-drvqueryjobattributes.md) function. All member values are function-supplied.

## -struct-fields

### -field dwJobNumberOfPagesPerSide

Number of document pages to be placed on one side of a physical page, as requested by the user. Allowable values are 1, 2, 4, 6, 9, or 16.

### -field dwDrvNumberOfPagesPerSide

Number of document pages that the printer and driver can place on one side of a physical page. This value must be 1 or the value specified for **dwJobNumberOfPagesPerSide**.

### -field dwNupBorderFlags

One of the following bit flag values:

| Flag | Definition |
|---|---|
| BORDER_PRINT | The print processor should draw a border around the page. |
| NO_BORDER_PRINT | The print processor should not draw a border around the page. |

### -field dwJobPageOrderFlags

One of the following bit flag values:

| Flag | Definition |
|---|---|
| BOOKLET_PRINT | Pages should be printed in booklet form, with two document pages printed on one side of a physical page. In landscape mode, the two document pages are printed side-by-side on the paper. In portrait mode, the two document pages are printed top-and-bottom. |
| NORMAL_PRINT | Pages should be printed in normal order: page 1, page 2, and so on. |
| REVERSE_PRINT | Pages should be printed in reverse order: last page, next-to-last page, and so on. |

### -field dwDrvPageOrderFlags

Bit flags indicating which page ordering options are supported by the printer and driver. Uses the same flags as **dwJobPageOrderFlags**.

### -field dwJobNumberOfCopies

Number of copies of the print job, as requested by the user.

### -field dwDrvNumberOfCopies

Maximum number of copies the printer and driver can handle at once, taking into account such job attributes as collating and stapling.

## -remarks

The caller (the EMF print processor) uses the **dwJobNumberOfPagesPerSide** and **dwDrvNumberOfPagesPerSide** members to determine whether the driver or the print processor handles "N-up" printing.

If the print processor handles "N-up" printing, it checks **dwNupBorderFlags** to determine if it should draw a page border.

The print processor checks **dwJobPageOrderFlags** and **dwDrvPageOrderFlags** to determine the order in which pages should be sent to the printer.

The print processor uses **dwJobNumberOfCopies** and **dwDrvNumberOfCopies** to determine the number of times the print job must be sent to the printer.

## -see-also

[DrvQueryJobAttributes](./nf-winddiui-drvqueryjobattributes.md)