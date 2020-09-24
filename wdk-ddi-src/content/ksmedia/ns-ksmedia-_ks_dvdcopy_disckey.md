---
UID: NS:ksmedia._KS_DVDCOPY_DISCKEY
title: _KS_DVDCOPY_DISCKEY (ksmedia.h)
description: The KS_DVDCOPY_DISCKEY structure is used to describe the disc key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_disckey.htm
tech.root: stream
ms.assetid: c7015bb6-1dd1-46b7-81b3-1762e5286c74
ms.date: 04/23/2018
keywords: ["KS_DVDCOPY_DISCKEY structure"]
ms.keywords: "*PKS_DVDCOPY_DISCKEY, KS_DVDCOPY_DISCKEY, KS_DVDCOPY_DISCKEY structure [Streaming Media Devices], PKS_DVDCOPY_DISCKEY, PKS_DVDCOPY_DISCKEY structure pointer [Streaming Media Devices], _KS_DVDCOPY_DISCKEY, dvdref_125d99fe-df42-4e9a-b21c-198c968ff88b.xml, ksmedia/KS_DVDCOPY_DISCKEY, ksmedia/PKS_DVDCOPY_DISCKEY, stream.ks_dvdcopy_disckey"
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
targetos: Windows
req.typenames: KS_DVDCOPY_DISCKEY, *PKS_DVDCOPY_DISCKEY
f1_keywords:
 - _KS_DVDCOPY_DISCKEY
 - ksmedia/_KS_DVDCOPY_DISCKEY
 - PKS_DVDCOPY_DISCKEY
 - ksmedia/PKS_DVDCOPY_DISCKEY
 - KS_DVDCOPY_DISCKEY
 - ksmedia/KS_DVDCOPY_DISCKEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DVDCOPY_DISCKEY
---

# _KS_DVDCOPY_DISCKEY structure


## -description

The KS_DVDCOPY_DISCKEY structure is used to describe the disc key information for the DVD copyright protection authentication process.

## -struct-fields

### -field DiscKey

Specifies the DVD's disc key.

## -remarks

The KS_DVDCOPY_DISCKEY structure is used by the <a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-disc-key">KSPROPERTY_DVDCOPY_DISC_KEY</a> property.

For more information, see <a href="/windows-hardware/drivers/stream/dvd-copyright-protection">DVD Copyright Protection</a>.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-disc-key">KSPROPERTY_DVDCOPY_DISC_KEY</a>