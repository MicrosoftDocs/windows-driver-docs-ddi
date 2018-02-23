---
UID: NS:ksmedia.KS_AM_ExactRateChange
title: KS_AM_ExactRateChange
author: windows-driver-content
description: The KS_AM_ExactRateChange structure is not yet implemented.
old-location: stream\ks_am_exactratechange.htm
old-project: stream
ms.assetid: c7ffc52a-e7cd-4ba1-9696-568719166713
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PKS_AM_ExactRateChange structure pointer [Streaming Media Devices], dvdref_bbe80dae-5cb8-45f8-a283-c0a2af794525.xml, *PKS_AM_ExactRateChange, ksmedia/KS_AM_ExactRateChange, PKS_AM_ExactRateChange, KS_AM_ExactRateChange structure [Streaming Media Devices], KS_AM_ExactRateChange, ksmedia/PKS_AM_ExactRateChange, stream.ks_am_exactratechange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
apiname:
-	KS_AM_ExactRateChange
product: Windows
targetos: Windows
req.typenames: KS_AM_ExactRateChange, *PKS_AM_ExactRateChange
---

# KS_AM_ExactRateChange structure


## -description


The KS_AM_ExactRateChange structure is not yet implemented.


## -syntax


````
typedef struct {
  REFERENCE_TIME OutputZeroTime;
  LONG           Rate;
} KS_AM_ExactRateChange, *PKS_AM_ExactRateChange;
````


## -struct-fields




### -field OutputZeroTime

Indicates an "input" time stamp that maps to a zero output time stamp.


### -field Rate

Specifies the new rate. This value is multiplied by 10000 (decimal).


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567280">KS_AM_RATE_ExactRateChange</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AM_ExactRateChange structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

