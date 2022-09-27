---
UID: NS:printoem._CUSTOMSIZEPARAM
title: CUSTOMSIZEPARAM (printoem.h)
description: The CUSTOMSIZEPARAM structure holds information pertaining to a single custom page size parameter for a printer.
tech.root: print
ms.date: 08/12/2022
keywords: ["CUSTOMSIZEPARAM structure"]
ms.keywords: "*PCUSTOMSIZEPARAM, CUSTOMSIZEPARAM, CUSTOMSIZEPARAM structure [Print Devices], PCUSTOMSIZEPARAM, PCUSTOMSIZEPARAM structure pointer [Print Devices], _CUSTOMSIZEPARAM, print.customsizeparam, print_unidrv-pscript_ui_ca016241-b74a-43d1-9b45-4deece484d10.xml, printoem/CUSTOMSIZEPARAM, printoem/PCUSTOMSIZEPARAM"
req.header: printoem.h
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
req.typenames: CUSTOMSIZEPARAM, *PCUSTOMSIZEPARAM
f1_keywords:
 - _CUSTOMSIZEPARAM
 - printoem/_CUSTOMSIZEPARAM
 - PCUSTOMSIZEPARAM
 - printoem/PCUSTOMSIZEPARAM
 - CUSTOMSIZEPARAM
 - printoem/CUSTOMSIZEPARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _CUSTOMSIZEPARAM
 - PCUSTOMSIZEPARAM
 - CUSTOMSIZEPARAM
---

## -description

The **CUSTOMSIZEPARAM** structure holds information pertaining to a single custom page size parameter for a printer.

## -struct-fields

### -field dwOrder

Specifies the order in which a custom page size parameter is placed on the PostScript interpreter's operand stack. For example, a parameter for which **dwOrder** is set to 1 is placed on the stack first. A parameter for which **dwOrder** is set to 2 is placed on the stack second, and so on.

### -field lMinVal

Specifies the minimum value of the custom page size parameter.

### -field lMaxVal

Specifies the maximum value of the custom page size parameter.

## -remarks

The custom page size parameters include Width, Height, WidthOffset, HeightOffset, and Orientation. For Orientation, **lMinVal** and **lMaxVal** are values in the range [0, 3]. For the other custom page size parameters, **lMinVal** and **lMaxVal** values are in units of microns.

## -see-also

[EATTRIBUTE_DATATYPE](./ne-printoem-_eattribute_datatype.md)