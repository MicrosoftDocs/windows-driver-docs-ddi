---
UID: NS:ks.KSALLOCATOR_FRAMING_EX
title: KSALLOCATOR_FRAMING_EX
author: windows-driver-content
description: The KSALLOCATOR_FRAMING_EX structure is the AVStream replacement for KSALLOCATOR_FRAMING. KSALLOCATOR_FRAMING_EX defines allocator requirements on a pin in a kernel level filter.
old-location: stream\ksallocator_framing_ex.htm
old-project: stream
ms.assetid: 39101009-ba03-472b-8664-d00c7a5cd335
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSALLOCATOR_FRAMING_EX, KSALLOCATOR_FRAMING_EX, KSALLOCATOR_FRAMING_EX structure [Streaming Media Devices], PKSALLOCATOR_FRAMING_EX, PKSALLOCATOR_FRAMING_EX structure pointer [Streaming Media Devices], ks-struct_d2aa8aab-1778-4383-b524-d52e4dd6c4c2.xml, ks/KSALLOCATOR_FRAMING_EX, ks/PKSALLOCATOR_FRAMING_EX, stream.ksallocator_framing_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSALLOCATOR_FRAMING_EX
product:
- Windows
targetos: Windows
req.typenames: KSALLOCATOR_FRAMING_EX, *PKSALLOCATOR_FRAMING_EX
---

# KSALLOCATOR_FRAMING_EX structure


## -description


The KSALLOCATOR_FRAMING_EX structure is the AVStream replacement for KSALLOCATOR_FRAMING. KSALLOCATOR_FRAMING_EX defines allocator requirements on a pin in a kernel level filter.


## -struct-fields




### -field CountItems

Specifies the number of framing items that are present in the <b>FramingItem</b> array.


### -field PinFlags

Reserved, set to zero.


### -field OutputCompression

Points to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567312">KS_COMPRESSION</a> that defines the frame ratio for transforms that change the size of a frame.


### -field PinWeight

This pin framing's weight graph-wide. Reserved, set to zero.


### -field FramingItem

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567646">KS_FRAMING_ITEM</a> structures specifying the actual framing items.


## -remarks



A minidriver can also use DECLARE_SIMPLE_FRAMING_EX to declare an extended framing structure in line with the original structure. This macro is defined in <i>Ks.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define DECLARE_SIMPLE_FRAMING_EX(FramingExName, MemoryType, Flags, Frames, Alignment, MinFrameSize, MaxFrameSize) const KSALLOCATOR_FRAMING_EX FramingExName</pre>
</td>
</tr>
</table></span></div>
DECLARE_SIMPLE_FRAMING_EX declares a KSALLOCATOR_FRAMING_EX structure called <b>FramingExName</b> with the specified memory type (often either STATIC_KS_TYPE_DONT_CARE or one of the kernel paged or nonpaged GUIDs). The <b>Frames</b> and <b>Alignment</b> fields of the macro correspond to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560979">KSALLOCATOR_FRAMING</a>. <b>MinFrameSize</b> and <b>MaxFrameSize</b> ensure that frames are within a specific size range. Flags corresponds to the <b>OptionsFlags</b> and <b>RequirementsFlags</b> in <b>KSALLOCATOR_FRAMING</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560979">KSALLOCATOR_FRAMING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567312">KS_COMPRESSION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567646">KS_FRAMING_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567647">KS_FRAMING_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567648">KS_FRAMING_RANGE_WEIGHTED</a>
 

 

