---
UID: NS:ksmedia._KS_DVDCOPY_BUSKEY
title: _KS_DVDCOPY_BUSKEY (ksmedia.h)
description: The KS_DVDCOPY_BUSKEY structure is used to describe the bus key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_buskey.htm
tech.root: stream
ms.assetid: bae613e1-c450-4bc0-9370-a7eb8438ae23
ms.date: 04/23/2018
keywords: ["KS_DVDCOPY_BUSKEY structure"]
ms.keywords: "*PKS_DVDCOPY_BUSKEY, KS_DVDCOPY_BUSKEY, KS_DVDCOPY_BUSKEY structure [Streaming Media Devices], PKS_DVDCOPY_BUSKEY, PKS_DVDCOPY_BUSKEY structure pointer [Streaming Media Devices], _KS_DVDCOPY_BUSKEY, dvdref_e3933026-ef22-42c4-8977-2c648421ccb2.xml, ksmedia/KS_DVDCOPY_BUSKEY, ksmedia/PKS_DVDCOPY_BUSKEY, stream.ks_dvdcopy_buskey"
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
req.typenames: KS_DVDCOPY_BUSKEY, *PKS_DVDCOPY_BUSKEY
f1_keywords:
 - _KS_DVDCOPY_BUSKEY
 - ksmedia/_KS_DVDCOPY_BUSKEY
 - PKS_DVDCOPY_BUSKEY
 - ksmedia/PKS_DVDCOPY_BUSKEY
 - KS_DVDCOPY_BUSKEY
 - ksmedia/KS_DVDCOPY_BUSKEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DVDCOPY_BUSKEY
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

The KS_DVDCOPY_BUSKEY structure is used by both the <a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-dvd-key1">KSPROPERTY_DVDCOPY_DVD_KEY1</a> and <a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-dec-key2">KSPROPERTY_DVDCOPY_DEC_KEY2</a> properties.

For more information, see <a href="/windows-hardware/drivers/stream/dvd-copyright-protection">DVD Copyright Protection</a>.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-dec-key2">KSPROPERTY_DVDCOPY_DEC_KEY2</a>



<a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-dvd-key1">KSPROPERTY_DVDCOPY_DVD_KEY1</a>