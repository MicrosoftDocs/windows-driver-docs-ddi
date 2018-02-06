---
UID: NS:ks.KS_FRAMING_RANGE
title: KS_FRAMING_RANGE
author: windows-driver-content
description: The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item.
old-location: stream\ks_framing_range.htm
old-project: stream
ms.assetid: 3263b290-2966-4e19-9828-b91e7b2efa55
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/PKS_FRAMING_RANGE, ks/KS_FRAMING_RANGE, KS_FRAMING_RANGE, stream.ks_framing_range, ks-struct_a489de91-e530-4185-9344-0ab4fe426cc8.xml, PKS_FRAMING_RANGE, *PKS_FRAMING_RANGE, KS_FRAMING_RANGE structure [Streaming Media Devices], PKS_FRAMING_RANGE structure pointer [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KS_FRAMING_RANGE
product: Windows
targetos: Windows
req.typenames: "*PKS_FRAMING_RANGE, KS_FRAMING_RANGE"
---

# KS_FRAMING_RANGE structure


## -description


The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item.


## -syntax


````
typedef struct {
  ULONG MinFrameSize;
  ULONG MaxFrameSize;
  ULONG Stepping;
} KS_FRAMING_RANGE, *PKS_FRAMING_RANGE;
````


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

<a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a>

<a href="..\ks\ns-ks-ks_framing_item.md">KS_FRAMING_ITEM</a>

<a href="..\ks\ns-ks-ks_framing_range_weighted.md">KS_FRAMING_RANGE_WEIGHTED</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_FRAMING_RANGE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

