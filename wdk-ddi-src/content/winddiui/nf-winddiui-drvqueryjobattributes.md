---
UID: NF:winddiui.DrvQueryJobAttributes
title: DrvQueryJobAttributes function (winddiui.h)
description: The DrvQueryJobAttributes function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page (N-up printing), printing multiple copies of each page, collating pages, and printing pages in reverse order.
old-location: print\drvqueryjobattributes.htm
tech.root: print
ms.assetid: 71e07572-bb15-4838-94d1-e07a3305ab82
ms.date: 06/25/2020
keywords: ["DrvQueryJobAttributes function"]
ms.keywords: DrvQueryJobAttributes, DrvQueryJobAttributes function [Print Devices], print.drvqueryjobattributes, print_interface-graphics_3fc2f9a4-bfe5-4323-a73e-6ac3ca9cf217.xml, winddiui/DrvQueryJobAttributes
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
 - DrvQueryJobAttributes
 - winddiui/DrvQueryJobAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvQueryJobAttributes
---

# DrvQueryJobAttributes function


## -description

The **DrvQueryJobAttributes** function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page ("N-up" printing), printing multiple copies of each page, collating pages, and printing pages in reverse order.

## -parameters

### -param hPrinter 

[in]
Caller-supplied printer handle.

### -param pDevMode 

[in]
Caller-supplied pointer to a [DEVMODEW](https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew) structure.

### -param dwLevel 

[in]
Caller-supplied value indicating the type of structure pointed to by *lpAttributeInfo*, as indicated in the following table.

| *dwLevel* value | ColumStructure pointed to by *lpAttributeInfo* |
|--|--|
| 1 | [ATTRIBUTE_INFO_1](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_1) |
| 2 | [ATTRIBUTE_INFO_2](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_2) |
| 3 | [ATTRIBUTE_INFO_3](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3) |
| 4 | [ATTRIBUTE_INFO_4](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_4) |

### -param lpAttributeInfo 

[out]
Caller-supplied pointer to a structure identified by *dwLevel*.

## -returns

If the operation succeeds, the function should return **TRUE**. Otherwise, it should return **FALSE**. Returning **FALSE** causes the current print job to be canceled.

## -remarks

A [printer interface DLL](https://docs.microsoft.com/windows-hardware/drivers/print/printer-interface-dll) can optionally provide a **DrvQueryJobAttributes** function. If the function is provided, it should fill in the supplied structure, described by *dwLevel* and *plAttributeInfo*, to indicate the current print job's user-requested attributes (such as N-up parameters and the number of copies) and the driver's ability to support those attributes. The function is typically called by the EMF print processor, so it can determine which job attributes can be handled by the driver (or printer), and which must be handled by the print processor.

## -see-also

[ATTRIBUTE_INFO_1](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_1)

[ATTRIBUTE_INFO_2](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_2)

[ATTRIBUTE_INFO_3](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3)

[ATTRIBUTE_INFO_4](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_4)

