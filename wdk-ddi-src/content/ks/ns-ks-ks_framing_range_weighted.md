---
UID: NS:ks.KS_FRAMING_RANGE_WEIGHTED
title: KS_FRAMING_RANGE_WEIGHTED
author: windows-driver-content
description: Drivers can use the KS_FRAMING_RANGE_WEIGHTED structure to specify a range of weighted frame sizes.
old-location: stream\ks_framing_range_weighted.htm
old-project: stream
ms.assetid: a52cde43-f440-4e58-97b7-b2aac5fb5f6a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_FRAMING_RANGE_WEIGHTED, KS_FRAMING_RANGE_WEIGHTED, *PKS_FRAMING_RANGE_WEIGHTED
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
req.alt-api: KS_FRAMING_RANGE_WEIGHTED
req.alt-loc: ks.h
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
req.typenames: KS_FRAMING_RANGE_WEIGHTED, *PKS_FRAMING_RANGE_WEIGHTED
---

# KS_FRAMING_RANGE_WEIGHTED structure



## -description
Drivers can use the KS_FRAMING_RANGE_WEIGHTED structure to specify a range of weighted frame sizes.



## -syntax

````
typedef struct {
  KS_FRAMING_RANGE Range;
  ULONG            InPlaceWeight;
  ULONG            NotInPlaceWeight;
} KS_FRAMING_RANGE_WEIGHTED, *PKS_FRAMING_RANGE_WEIGHTED;
````


## -struct-fields

### -field Range

Specifies the framing range.


### -field InPlaceWeight

Not currently supported. Drivers should set to zero.


### -field NotInPlaceWeight

Not currently supported. Drivers should set to zero.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ks_framing_item.md">KS_FRAMING_ITEM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_FRAMING_RANGE_WEIGHTED structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

