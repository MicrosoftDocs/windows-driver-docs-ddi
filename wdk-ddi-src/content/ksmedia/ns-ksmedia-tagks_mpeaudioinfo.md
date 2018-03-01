---
UID: NS:ksmedia.tagKS_MPEAUDIOINFO
title: tagKS_MPEAUDIOINFO
author: windows-driver-content
description: The KS_MPEGAUDIOINFO structure describes an MPEG audio stream.
old-location: stream\ks_mpegaudioinfo.htm
old-project: stream
ms.assetid: df8a1e95-211a-47df-a904-4578cd0a7dc9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_MPEGAUDIOINFO, KS_MPEGAUDIOINFO, KS_MPEGAUDIOINFO structure [Streaming Media Devices], PKS_MPEGAUDIOINFO, PKS_MPEGAUDIOINFO structure pointer [Streaming Media Devices], ksmedia/KS_MPEGAUDIOINFO, ksmedia/PKS_MPEGAUDIOINFO, stream.ks_mpegaudioinfo, tagKS_MPEAUDIOINFO, vidcapstruct_613d53ce-69cd-46da-9bd8-0ac41ca12129.xml"
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
-	KS_MPEGAUDIOINFO
product: Windows
targetos: Windows
req.typenames: KS_MPEGAUDIOINFO, *PKS_MPEGAUDIOINFO
---

# tagKS_MPEAUDIOINFO structure


## -description


The KS_MPEGAUDIOINFO structure describes an MPEG audio stream.


## -syntax


````
typedef struct tagKS_MPEAUDIOINFO {
  DWORD dwFlags;
  DWORD dwReserved1;
  DWORD dwReserved2;
  DWORD dwReserved3;
} KS_MPEGAUDIOINFO, *PKS_MPEGAUDIOINFO;
````


## -struct-fields




### -field dwFlags

Specifies the time base for audio timestamps. Reject the connection if undefined bits are not 0. The following flag is defined.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_MPEGAUDIOINFO_27MhzTimebase

</td>
<td>
Specifies that PTS and DTS timestamps advance at 27 MHz rather than 90 kHz.

</td>
</tr>
</table>
 


### -field dwReserved1

Must be 0; otherwise, reject the connection.


### -field dwReserved2

Must be 0; otherwise, reject the connection.


### -field dwReserved3

Must be 0; otherwise, reject the connection.

