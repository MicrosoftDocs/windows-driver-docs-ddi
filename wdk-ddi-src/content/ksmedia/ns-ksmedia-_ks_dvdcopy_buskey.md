---
UID: NS:ksmedia._KS_DVDCOPY_BUSKEY
title: "_KS_DVDCOPY_BUSKEY"
author: windows-driver-content
description: The KS_DVDCOPY_BUSKEY structure is used to describe the bus key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_buskey.htm
old-project: stream
ms.assetid: bae613e1-c450-4bc0-9370-a7eb8438ae23
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKS_DVDCOPY_BUSKEY, KS_DVDCOPY_BUSKEY, KS_DVDCOPY_BUSKEY structure [Streaming Media Devices], PKS_DVDCOPY_BUSKEY, PKS_DVDCOPY_BUSKEY structure pointer [Streaming Media Devices], _KS_DVDCOPY_BUSKEY, dvdref_e3933026-ef22-42c4-8977-2c648421ccb2.xml, ksmedia/KS_DVDCOPY_BUSKEY, ksmedia/PKS_DVDCOPY_BUSKEY, stream.ks_dvdcopy_buskey"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KS_DVDCOPY_BUSKEY
product:
- Windows
targetos: Windows
req.typenames: KS_DVDCOPY_BUSKEY, *PKS_DVDCOPY_BUSKEY
---

# _KS_DVDCOPY_BUSKEY structure


## -description


The KS_DVDCOPY_BUSKEY structure is used to describe the bus key information for the DVD copyright protection authentication process.


## -struct-fields




### -field BusKey

Specifies the DVD decoder minidriver's bus key.


### -field Reserved

Reserved. Do not use.


## -remarks



The KS_DVDCOPY_BUSKEY structure is used by both the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565145">KSPROPERTY_DVDCOPY_DVD_KEY1</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff565142">KSPROPERTY_DVDCOPY_DEC_KEY2</a> properties.

For more information, see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565142">KSPROPERTY_DVDCOPY_DEC_KEY2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565145">KSPROPERTY_DVDCOPY_DVD_KEY1</a>
 

 

