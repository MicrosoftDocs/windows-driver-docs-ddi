---
UID: NS:ks.KS_FRAMING_RANGE
title: KS_FRAMING_RANGE
author: windows-driver-content
description: The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item.
old-location: stream\ks_framing_range.htm
old-project: stream
ms.assetid: 3263b290-2966-4e19-9828-b91e7b2efa55
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKS_FRAMING_RANGE, KS_FRAMING_RANGE, KS_FRAMING_RANGE structure [Streaming Media Devices], PKS_FRAMING_RANGE, PKS_FRAMING_RANGE structure pointer [Streaming Media Devices], ks-struct_a489de91-e530-4185-9344-0ab4fe426cc8.xml, ks/KS_FRAMING_RANGE, ks/PKS_FRAMING_RANGE, stream.ks_framing_range"
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
-	KS_FRAMING_RANGE
product:
- Windows
targetos: Windows
req.typenames: KS_FRAMING_RANGE, *PKS_FRAMING_RANGE
---

# KS_FRAMING_RANGE structure


## -description


The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item.


## -struct-fields




### -field MinFrameSize

Specifies a minimum frame size of type ULONG.


### -field MaxFrameSize

Specifies a maximum frame size of type ULONG.


### -field Stepping

Specifies the step value that should be used to create legal values within the range defined in <b>MinFrameSize</b> and <b>MaxFrameSize</b>.


## -remarks



When specifying the <b>Stepping</b> member, ensure that the value does not exceed the difference between the <b>MinFrameSize</b> and <b>MaxFrameSize</b> members. Otherwise, unpredictable behavior may result.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560979">KSALLOCATOR_FRAMING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567646">KS_FRAMING_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567648">KS_FRAMING_RANGE_WEIGHTED</a>
 

 

