---
UID: NS:ksmedia._KS_DVDCOPY_DISCKEY
title: _KS_DVDCOPY_DISCKEY
author: windows-driver-content
description: The KS_DVDCOPY_DISCKEY structure is used to describe the disc key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_disckey.htm
old-project: stream
ms.assetid: c7015bb6-1dd1-46b7-81b3-1762e5286c74
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKS_DVDCOPY_DISCKEY, *PKS_DVDCOPY_DISCKEY, dvdref_125d99fe-df42-4e9a-b21c-198c968ff88b.xml, KS_DVDCOPY_DISCKEY, PKS_DVDCOPY_DISCKEY structure pointer [Streaming Media Devices], ksmedia/PKS_DVDCOPY_DISCKEY, stream.ks_dvdcopy_disckey, ksmedia/KS_DVDCOPY_DISCKEY, KS_DVDCOPY_DISCKEY structure [Streaming Media Devices], _KS_DVDCOPY_DISCKEY
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
-	KS_DVDCOPY_DISCKEY
product: Windows
targetos: Windows
req.typenames: *PKS_DVDCOPY_DISCKEY, KS_DVDCOPY_DISCKEY
---

# _KS_DVDCOPY_DISCKEY structure


## -description


The KS_DVDCOPY_DISCKEY structure is used to describe the disc key information for the DVD copyright protection authentication process.


## -syntax


````
typedef struct _KS_DVDCOPY_DISCKEY {
  BYTE DiscKey[2048];
} KS_DVDCOPY_DISCKEY, *PKS_DVDCOPY_DISCKEY;
````


## -struct-fields




### -field DiscKey

Specifies the DVD's disc key.


## -remarks


The KS_DVDCOPY_DISCKEY structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565144">KSPROPERTY_DVDCOPY_DISC_KEY</a> property.

For more information, see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565144">KSPROPERTY_DVDCOPY_DISC_KEY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPY_DISCKEY structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

