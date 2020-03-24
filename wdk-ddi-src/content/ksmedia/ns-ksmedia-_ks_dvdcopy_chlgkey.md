---
UID: NS:ksmedia._KS_DVDCOPY_CHLGKEY
title: _KS_DVDCOPY_CHLGKEY (ksmedia.h)
description: The KS_DVDCOPY_CHLGKEY structure is used to describe the challenge key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_chlgkey.htm
tech.root: stream
ms.assetid: 10be15fc-ca0e-40d4-8fe9-9682478f5c5b
ms.date: 04/23/2018
keywords: ["_KS_DVDCOPY_CHLGKEY structure"]
ms.keywords: "*PKS_DVDCOPY_CHLGKEY, KS_DVDCOPY_CHLGKEY, KS_DVDCOPY_CHLGKEY structure [Streaming Media Devices], PKS_DVDCOPY_CHLGKEY, PKS_DVDCOPY_CHLGKEY structure pointer [Streaming Media Devices], _KS_DVDCOPY_CHLGKEY, dvdref_af25bbe5-5caf-4cd7-be78-1d905a50ef82.xml, ksmedia/KS_DVDCOPY_CHLGKEY, ksmedia/PKS_DVDCOPY_CHLGKEY, stream.ks_dvdcopy_chlgkey"
f1_keywords:
 - "ksmedia/KS_DVDCOPY_CHLGKEY"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KS_DVDCOPY_CHLGKEY
product:
- Windows
targetos: Windows
req.typenames: KS_DVDCOPY_CHLGKEY, *PKS_DVDCOPY_CHLGKEY
---

# _KS_DVDCOPY_CHLGKEY structure


## -description


The KS_DVDCOPY_CHLGKEY structure is used to describe the challenge key information for the DVD copyright protection authentication process.


## -struct-fields




### -field ChlgKey

Specifies the DVD decoder minidriver's challenge key.


### -field Reserved

Reserved. Do not use.


## -remarks



The KS_DVDCOPY_CHLGKEY structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-dvdcopy-chlg-key">KSPROPERTY_DVDCOPY_CHLG_KEY</a> property.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/dvd-copyright-protection">DVD Copyright Protection</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-dvdcopy-chlg-key">KSPROPERTY_DVDCOPY_CHLG_KEY</a>
 

 

