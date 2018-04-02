---
UID: NE:avcstrm._AVCSTRM_FORMAT
title: "_AVCSTRM_FORMAT"
author: windows-driver-content
description: The AVCSTRM_FUNCTION enumeration defines the AV/C subunit stream formats supported by avcstrm.sys.
old-location: stream\avcstrm_format.htm
old-project: stream
ms.assetid: 4481ec67-55b6-479e-b0b6-5f8ed56a5290
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVCSTRM_FORMAT, AVCSTRM_FORMAT enumeration [Streaming Media Devices], AVCSTRM_FORMAT_HDDV_NTSC, AVCSTRM_FORMAT_HDDV_PAL, AVCSTRM_FORMAT_MPEG2TS, AVCSTRM_FORMAT_SDDV_NTSC, AVCSTRM_FORMAT_SDDV_PAL, AVCSTRM_FORMAT_SDLDV_NTSC, AVCSTRM_FORMAT_SDLDV_PAL, _AVCSTRM_FORMAT, avcsref_489c2bf8-1e1f-4feb-91fb-0ba3666ba399.xml, avcstrm/AVCSTRM_FORMAT, avcstrm/AVCSTRM_FORMAT_HDDV_NTSC, avcstrm/AVCSTRM_FORMAT_HDDV_PAL, avcstrm/AVCSTRM_FORMAT_MPEG2TS, avcstrm/AVCSTRM_FORMAT_SDDV_NTSC, avcstrm/AVCSTRM_FORMAT_SDDV_PAL, avcstrm/AVCSTRM_FORMAT_SDLDV_NTSC, avcstrm/AVCSTRM_FORMAT_SDLDV_PAL, stream.avcstrm_format
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	AVCSTRM_FORMAT
product:
- Windows
targetos: Windows
req.typenames: AVCSTRM_FORMAT
---

# _AVCSTRM_FORMAT enumeration


## -description


The AVCSTRM_FUNCTION enumeration defines the AV/C subunit stream formats supported by <i>avcstrm.sys</i>.


## -enum-fields




### -field AVCSTRM_FORMAT_SDDV_NTSC

Specifies the 61883-2 specification for SD-DVCR data transmission, Standard Definition NTSC.


### -field AVCSTRM_FORMAT_SDDV_PAL

Specifies the 61883-2 specification for SD-DVCR data transmission, Standard Definition PAL.


### -field AVCSTRM_FORMAT_MPEG2TS

Specifies the 61883-4 specification for MPEG2-TS data transmission.


### -field AVCSTRM_FORMAT_HDDV_NTSC

Specifies the 61883-3 specification for HD-DVCR data transmission, High Definition NTSC. This format is not supported.


### -field AVCSTRM_FORMAT_HDDV_PAL

Specifies the 61883-3 specification for HD-DVCR data transmission, High Definition PAL. This format is not supported.


### -field AVCSTRM_FORMAT_SDLDV_NTSC

Specifies the 61883-5 specification for SDL-DVCR data transmission. NTSC. This format is not supported.


### -field AVCSTRM_FORMAT_SDLDV_PAL

Specifies the 61883-5 specification for SDL-DVCR data transmission. PAL. This format is not supported.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554117">AVCSTRM_FORMAT_INFO</a>
 

 

