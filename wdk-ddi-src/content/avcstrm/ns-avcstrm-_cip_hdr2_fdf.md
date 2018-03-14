---
UID: NS:avcstrm._CIP_HDR2_FDF
title: "_CIP_HDR2_FDF"
author: windows-driver-content
description: The CIP_HDR2_FDF structure describes the second quadlet of a CIP header pair.
old-location: stream\cip_hdr2_fdf.htm
old-project: stream
ms.assetid: 10f01d72-25cc-4a5a-b6e3-8475f09b12e4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PCIP_HDR2_FDF, CIP_HDR2_FDF, CIP_HDR2_FDF structure [Streaming Media Devices], PCIP_HDR2_FDF, PCIP_HDR2_FDF structure pointer [Streaming Media Devices], _CIP_HDR2_FDF, avcsref_47436092-ff0a-4bd4-97f2-a241da9f328a.xml, avcstrm/CIP_HDR2_FDF, avcstrm/PCIP_HDR2_FDF, stream.cip_hdr2_fdf"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	avcstrm.h
api_name:
-	CIP_HDR2_FDF
product: Windows
targetos: Windows
req.typenames: CIP_HDR2_FDF, *PCIP_HDR2_FDF
---

# _CIP_HDR2_FDF structure


## -description


The CIP_HDR2_FDF structure describes the second quadlet of a CIP header pair.


## -syntax


````
typedef struct _CIP_HDR2_FDF {
  ULONG FDF  :24;
  ULONG FMT  :6;
  ULONG Bit10  :2;
} CIP_HDR2_FDF, *PCIP_HDR2_FDF;
````


## -struct-fields




### -field FDF

Format dependent field. This is not used for opening a stream. These must be set to 0.


### -field FMT

CIP format. For example, 000000 = DV and 100000 = MPEG2TS.


### -field Bit10

Must be set to 1:0


## -see-also

<a href="..\avcstrm\ns-avcstrm-_cip_hdr1.md">CIP_HDR1</a>



 

 


