---
UID: NS:avcstrm._CIP_HDR1
title: "_CIP_HDR1"
author: windows-driver-content
description: The CIP_HDR1 structure describes the generic data structure of the two quadlet CIP headers (first quadlet of the pair).
old-location: stream\cip_hdr1.htm
old-project: stream
ms.assetid: 15450f33-cb86-4c1d-87d7-2d77a1d66a81
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PCIP_HDR1, _CIP_HDR1, CIP_HDR1, avcstrm/CIP_HDR1, avcstrm/PCIP_HDR1, PCIP_HDR1 structure pointer [Streaming Media Devices], avcsref_bfb761c5-6eb2-459a-b75f-32c5e2d11700.xml, CIP_HDR1 structure [Streaming Media Devices], *PCIP_HDR1, stream.cip_hdr1
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
-	CIP_HDR1
product: Windows
targetos: Windows
req.typenames: "*PCIP_HDR1, CIP_HDR1"
---

# _CIP_HDR1 structure


## -description


The CIP_HDR1 structure describes the generic data structure of the two quadlet CIP headers (first quadlet of the pair).


## -syntax


````
typedef struct _CIP_HDR1 {
  ULONG DBC  :8;
  ULONG Rsv00  :2;
  ULONG SPH  :1;
  ULONG QPC  :3;
  ULONG FN  :2;
  ULONG DBS  :8;
  ULONG SID  :6;
  ULONG Bit00  :2;
} CIP_HDR1, *PCIP_HDR1;
````


## -struct-fields




### -field DBC

Data block counter. This is not used by subunit driver. It must be set to 0.


### -field Rsv00

Reserved bits. Do not use this. It must be 0:0.


### -field SPH

Specifies a source packet header. A value of 1 indicates the presence of a source packet header. A value of 0 indicates no source packet header.


### -field QPC

Quadlet padding count (0..7 quadlets).


### -field FN

Specifies the fractional number.


### -field DBS

Specifies the data block size in quadlets.


### -field SID

Specifies the source node ID (ID of transmitter). Not used by the subunit driver. Must be set to 0.


### -field Bit00

Must be set to 0:0.


## -see-also

<a href="..\avcstrm\ns-avcstrm-_cip_hdr2_mpegts.md">CIP_HDR2_MPEGTS</a>

<a href="..\avcstrm\ns-avcstrm-_cip_hdr2_syt.md">CIP_HDR2_SYT</a>

<a href="..\avcstrm\ns-avcstrm-_cip_hdr2_fdf.md">CIP_HDR2_FDF</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20CIP_HDR1 structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

