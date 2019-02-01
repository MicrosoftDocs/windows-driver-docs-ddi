---
UID: NF:wdm.RtlEqualMemory
title: RtlEqualMemory macro (wdm.h)
description: The RtlEqualMemory routine compares two blocks of memory to determine whether the specified number of bytes are identical.
old-location: kernel\rtlequalmemory.htm
tech.root: kernel
ms.assetid: 43695fa9-32e1-4bd5-b146-88d6d03fe9fb
ms.date: 04/30/2018
ms.keywords: RtlEqualMemory, RtlEqualMemory routine [Kernel-Mode Driver Architecture], k109_a75dfbc8-12af-4f95-9ba0-b7752b796e55.xml, kernel.rtlequalmemory, wdm/RtlEqualMemory
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	RtlEqualMemory
-   memcmp
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlEqualMemory macro


## -description


The <b>RtlEqualMemory</b> routine compares two blocks of memory to determine whether the specified number of bytes are identical. 


## -parameters




### -param Destination [in]

Datatype: void*. A pointer to a caller-allocated block of memory to compare.


### -param Source [in]

Datatype: void*. A pointer to a caller-allocated block of memory that is compared to the block of memory to which <i>Source1</i> points.


### -param Length [in]

Datatype: size_t. Specifies the number of bytes to be compared.

## -returns
**RtlEqualMemory** returns TRUE if Source1 and Source2 are equivalent; otherwise, it returns FALSE. 


## -remarks



<b>RtlEqualMemory</b> begins the comparison with byte zero of each block.

Callers of <b>RtlEqualMemory</b> can be running at any IRQL if both blocks of memory are resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561778">RtlCompareMemory</a>
 

 

