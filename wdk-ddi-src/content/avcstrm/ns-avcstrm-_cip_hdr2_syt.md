---
UID: NS:avcstrm._CIP_HDR2_SYT
title: "_CIP_HDR2_SYT"
author: windows-driver-content
description: The CIP_HDR2_SYT structure describes the second quadlet of a CIP header pair for a DV format stream.
old-location: stream\cip_hdr2_syt.htm
old-project: stream
ms.assetid: e66b721f-4cc0-4d35-9e24-6d7dd4029ea4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avcstrm/CIP_HDR2_SYT, avcstrm/PCIP_HDR2_SYT, avcsref_1ea551ca-5d40-4bc3-bc54-b736fd6a2b23.xml, stream.cip_hdr2_syt, *PCIP_HDR2_SYT, PCIP_HDR2_SYT, CIP_HDR2_SYT structure [Streaming Media Devices], CIP_HDR2_SYT, PCIP_HDR2_SYT structure pointer [Streaming Media Devices], _CIP_HDR2_SYT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
-	avcstrm.h
apiname:
-	CIP_HDR2_SYT
product: Windows
targetos: Windows
req.typenames: "*PCIP_HDR2_SYT, CIP_HDR2_SYT"
---

# _CIP_HDR2_SYT structure


## -description


The CIP_HDR2_SYT structure describes the second quadlet of a CIP header pair for a DV format stream.


## -syntax


````
typedef struct _CIP_HDR2_SYT {
  ULONG SYT  :16;
  ULONG RSV  :2;
  ULONG STYPE  :5;
  ULONG F5060_OR_TSF  :1;
  ULONG FMT  :6;
  ULONG Bit10  :2;
} CIP_HDR2_SYT, *PCIP_HDR2_SYT;
````


## -struct-fields




### -field SYT

Lower 16 bits of CYCLE_TIME. This is not used for opening a stream.


### -field RSV

Must be set to 0:0.


### -field STYPE

Specifies the video signal type, which is used for transmitting real time data.


### -field F5060_OR_TSF

Specifies field encoding or time-shift flag depending on the value of FMT. This flag may be either 0 for NTSC or 1 for PAL, or 1 for TimeShiftFlag. This flag has multiple meanings (like a union) depending on the FMT member. If the FMT member indicates DV format, then this is either 50/60 flag (NTSC or PAL); if it is it MPEG-TS, then this is a time-shifting flag.


### -field FMT

CIP format ID. For example, 000000 = DV and 100000 = MPEG2TS. If this is 111111 (no data), then DBS, FN, SPH and DBC (in the first quadlet of the CIP header, <a href="..\avcstrm\ns-avcstrm-_cip_hdr1.md">CIP_HDR1</a>) are ignored.


### -field Bit10

Must be set to 1:0.


## -see-also

<a href="..\avcstrm\ns-avcstrm-_cip_hdr1.md">CIP_HDR1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20CIP_HDR2_SYT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

