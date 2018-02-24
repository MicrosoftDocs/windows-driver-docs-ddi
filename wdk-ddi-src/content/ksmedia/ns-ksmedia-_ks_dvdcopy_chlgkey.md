---
UID: NS:ksmedia._KS_DVDCOPY_CHLGKEY
title: "_KS_DVDCOPY_CHLGKEY"
author: windows-driver-content
description: The KS_DVDCOPY_CHLGKEY structure is used to describe the challenge key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_chlgkey.htm
old-project: stream
ms.assetid: 10be15fc-ca0e-40d4-8fe9-9682478f5c5b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ksmedia/KS_DVDCOPY_CHLGKEY, ksmedia/PKS_DVDCOPY_CHLGKEY, _KS_DVDCOPY_CHLGKEY, PKS_DVDCOPY_CHLGKEY structure pointer [Streaming Media Devices], KS_DVDCOPY_CHLGKEY, KS_DVDCOPY_CHLGKEY structure [Streaming Media Devices], PKS_DVDCOPY_CHLGKEY, dvdref_af25bbe5-5caf-4cd7-be78-1d905a50ef82.xml, stream.ks_dvdcopy_chlgkey, *PKS_DVDCOPY_CHLGKEY
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
-	KS_DVDCOPY_CHLGKEY
product: Windows
targetos: Windows
req.typenames: KS_DVDCOPY_CHLGKEY, *PKS_DVDCOPY_CHLGKEY
---

# _KS_DVDCOPY_CHLGKEY structure


## -description


The KS_DVDCOPY_CHLGKEY structure is used to describe the challenge key information for the DVD copyright protection authentication process.


## -syntax


````
typedef struct _KS_DVDCOPY_CHLGKEY {
  BYTE ChlgKey[10];
  BYTE Reserved[2];
} KS_DVDCOPY_CHLGKEY, *PKS_DVDCOPY_CHLGKEY;
````


## -struct-fields




### -field ChlgKey

Specifies the DVD decoder minidriver's challenge key.


### -field Reserved

Reserved. Do not use.


## -remarks



The KS_DVDCOPY_CHLGKEY structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565140">KSPROPERTY_DVDCOPY_CHLG_KEY</a> property.

For more information, see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565140">KSPROPERTY_DVDCOPY_CHLG_KEY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPY_CHLGKEY structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

