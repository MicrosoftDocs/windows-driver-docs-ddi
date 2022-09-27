---
UID: NS:printoem.__unnamed_struct_1
title: OEMMEMORYUSAGE (printoem.h)
description: The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's IPrintOemUni::MemoryUsage method.
tech.root: print
ms.date: 08/12/2022
keywords: ["OEMMEMORYUSAGE structure"]
ms.keywords: "*POEMMEMORYUSAGE, OEMMEMORYUSAGE, OEMMEMORYUSAGE structure [Print Devices], POEMMEMORYUSAGE, POEMMEMORYUSAGE structure pointer [Print Devices], print.oemmemoryusage, print_unidrv-pscript_rendering_c6746c1c-f6c5-4acf-bcd3-bc1f69382dae.xml, printoem/OEMMEMORYUSAGE, printoem/POEMMEMORYUSAGE"
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
req.typenames: OEMMEMORYUSAGE, *POEMMEMORYUSAGE
f1_keywords:
 - POEMMEMORYUSAGE
 - printoem/POEMMEMORYUSAGE
 - OEMMEMORYUSAGE
 - printoem/OEMMEMORYUSAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - POEMMEMORYUSAGE
 - OEMMEMORYUSAGE
---

## -description

The **OEMMEMORYUSAGE** structure is used as an input parameter to a rendering plug-in's [IPrintOemUni::MemoryUsage](../prcomoem/nf-prcomoem-iprintoemuni-memoryusage.md) method.

## -struct-fields

### -field dwFixedMemoryUsage

Specifies the amount, in bytes, of fixed-sized memory required by the **IPrintOemUni::MemoryUsage** method. Supplied by the rendering plug-in.

### -field dwPercentMemoryUsage

Specifies the amount of variably-sized memory required by the **IPrintOemUni::MemoryUsage** method, expressed as a percentage of the size of the source bitmap received by [IPrintOemUni::ImageProcessing](../prcomoem/nf-prcomoem-iprintoemuni-imageprocessing.md). Supplied by the rendering plug-in.

### -field dwMaxBandSize

Specifies the maximum size, in bytes, that can be used for source bitmaps. This is the value that Unidrv uses to subtract from when applying the plug-in supplied values contained in **dwFixedMemoryUsage** and **dwPercentMemoryUsage**. Supplied by Unidrv.

## -remarks

The Unidrv driver uses the values in the **dwFixedMemoryUsage** and **dwPercentMemoryUsage** members of this structure to determine the optimum size for a GDI drawing surface, taking into account any memory requirements of a rendering plug-in's **IPrintOemUni::ImageProcessing** method. For more information about how these members are used, see the Remarks section in [IPrintOemUni::MemoryUsage](../prcomoem/nf-prcomoem-iprintoemuni-memoryusage.md).

## -see-also

[IPrintOemUni::ImageProcessing](../prcomoem/nf-prcomoem-iprintoemuni-imageprocessing.md)

[IPrintOemUni::MemoryUsage](../prcomoem/nf-prcomoem-iprintoemuni-memoryusage.md)