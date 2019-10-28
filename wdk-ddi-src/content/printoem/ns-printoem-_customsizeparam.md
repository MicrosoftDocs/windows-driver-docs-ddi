---
UID: NS:printoem._CUSTOMSIZEPARAM
title: _CUSTOMSIZEPARAM (printoem.h)
description: The CUSTOMSIZEPARAM structure holds information pertaining to a single custom page size parameter for a printer.
old-location: print\customsizeparam.htm
tech.root: print
ms.assetid: 7ec0c38a-8614-417b-9ec3-678c7d80841f
ms.date: 04/20/2018
ms.keywords: "*PCUSTOMSIZEPARAM, CUSTOMSIZEPARAM, CUSTOMSIZEPARAM structure [Print Devices], PCUSTOMSIZEPARAM, PCUSTOMSIZEPARAM structure pointer [Print Devices], _CUSTOMSIZEPARAM, print.customsizeparam, print_unidrv-pscript_ui_ca016241-b74a-43d1-9b45-4deece484d10.xml, printoem/CUSTOMSIZEPARAM, printoem/PCUSTOMSIZEPARAM"
ms.topic: struct
f1_keywords:
 - "printoem/CUSTOMSIZEPARAM"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- printoem.h
api_name:
- CUSTOMSIZEPARAM
product:
- Windows
targetos: Windows
req.typenames: CUSTOMSIZEPARAM, *PCUSTOMSIZEPARAM
---

# _CUSTOMSIZEPARAM structure


## -description


The CUSTOMSIZEPARAM structure holds information pertaining to a single custom page size parameter for a printer.


## -struct-fields




### -field dwOrder

Specifies the order in which a custom page size parameter is placed on the PostScript interpreter's operand stack. For example, a parameter for which <b>dwOrder</b> is set to 1 is placed on the stack first. A parameter for which <b>dwOrder</b> is set to 2 is placed on the stack second, and so on.


### -field lMinVal

Specifies the minimum value of the custom page size parameter.


### -field lMaxVal

Specifies the maximum value of the custom page size parameter.


## -remarks



The custom page size parameters include Width, Height, WidthOffset, HeightOffset, and Orientation. For Orientation, <b>lMinVal</b> and <b>lMaxVal</b> are values in the range [0, 3]. For the other custom page size parameters, <b>lMinVal</b> and <b>lMaxVal</b> values are in units of microns.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ne-printoem-_eattribute_datatype">EATTRIBUTE_DATATYPE</a>
 

 

