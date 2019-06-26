---
UID: NS:ksmedia.__unnamed_struct_161
title: KS_AM_SimpleRateChange (ksmedia.h)
description: The KS_AM_SimpleRateChange structure is used to describe a simple rate change (fast-forward or rewind) for an MPEG2 stream.
old-location: stream\ks_am_simpleratechange.htm
tech.root: stream
ms.assetid: d797b377-6c27-41f9-932d-264d0e8b5dd0
ms.date: 04/30/2019
ms.keywords: "*PKS_AM_SimpleRateChange, KS_AM_SimpleRateChange, KS_AM_SimpleRateChange structure [Streaming Media Devices], PKS_AM_SimpleRateChange, PKS_AM_SimpleRateChange structure pointer [Streaming Media Devices], dvdref_8c318967-5f7d-4597-ab40-924e95b86dd7.xml, ksmedia/KS_AM_SimpleRateChange, ksmedia/PKS_AM_SimpleRateChange, stream.ks_am_simpleratechange"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KS_AM_SimpleRateChange
product:
- Windows
targetos: Windows
req.typenames: KS_AM_SimpleRateChange, *PKS_AM_SimpleRateChange
---

# KS_AM_SimpleRateChange structure


## -description


The KS_AM_SimpleRateChange structure is used to describe a simple rate change (fast-forward or rewind) for an MPEG2 stream.


## -struct-fields




### -field StartTime

Indicates the stream time at which to start this rate.


### -field Rate

Specifies the new rate. This value is multiplied by 10000 (decimal).


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-am-rate-simpleratechange">KS_AM_RATE_SimpleRateChange</a>
 

 

