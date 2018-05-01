---
UID: NS:bthioctl._BTH_SDP_STREAM_RESPONSE
title: "_BTH_SDP_STREAM_RESPONSE"
author: windows-driver-content
description: The BTH_SDP_STREAM_RESPONSE structure contains information about an SDP record.
old-location: bltooth\bth_sdp_stream_response.htm
old-project: bltooth
ms.assetid: 5b7db410-8d9c-4c3e-aaae-44f7d5b779a0
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: "*PBTH_SDP_STREAM_RESPONSE, BTH_SDP_STREAM_RESPONSE, BTH_SDP_STREAM_RESPONSE structure [Bluetooth Devices], PBTH_SDP_STREAM_RESPONSE, PBTH_SDP_STREAM_RESPONSE structure pointer [Bluetooth Devices], _BTH_SDP_STREAM_RESPONSE, bltooth.bth_sdp_stream_response, bth_structs_c48540ef-f38b-4821-84cd-2b781c0b5352.xml, bthioctl/BTH_SDP_STREAM_RESPONSE, bthioctl/PBTH_SDP_STREAM_RESPONSE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
-	bthioctl.h
api_name:
-	BTH_SDP_STREAM_RESPONSE
product: Windows
targetos: Windows
req.typenames: BTH_SDP_STREAM_RESPONSE, *PBTH_SDP_STREAM_RESPONSE
---

# _BTH_SDP_STREAM_RESPONSE structure


## -description


The BTH_SDP_STREAM_RESPONSE structure contains information about an SDP record.


## -struct-fields




### -field requiredSize

The size, in bytes, of the entire SDP record. This value can be useful if the output buffer is too
     small to hold the entire record.


### -field responseSize

The size, in bytes, of the raw SDP record stream that follows this structure.


### -field response

The first byte of the SDP record stream.


## -remarks



This structure is returned with a raw stream to the output buffer of the 
    <a href="https://msdn.microsoft.com/30daf70e-34d1-45f7-a69b-503e275b83af">
    IOCTL_BTH_SDP_ATTRIBUTE_SEARCH</a> and 
    <a href="https://msdn.microsoft.com/f0955e88-df80-4f53-bc5f-5a38a840aab4">
    IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a> IOCTLs.

The 
    <b>requiredSize</b> and 
    <b>responseSize</b> members are included in this structure because the raw SDP record stream does not
    contain these fields.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536687">IOCTL_BTH_SDP_ATTRIBUTE_SEARCH</a>



<a href="https://msdn.microsoft.com/f0955e88-df80-4f53-bc5f-5a38a840aab4">
   IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a>
 

 

