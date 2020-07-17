---
UID: NS:61883._CIP_STOP
title: _CIP_STOP (61883.h)
description: This structure is used to stop transmission or reception.
old-location: ieee\cip_stop.htm
tech.root: IEEE
ms.assetid: FE396C2C-B099-47F4-9C27-93D420D54103
ms.date: 02/15/2018
keywords: ["_CIP_STOP structure"]
ms.keywords: "*PCIP_STOP, 61883/CIP_STOP, 61883/PCIP_STOP, CIP_STOP, CIP_STOP structure [Buses], IEEE.cip_stop, PCIP_STOP, PCIP_STOP structure pointer [Buses], _CIP_STOP"
f1_keywords:
 - "61883/CIP_STOP"
 - "CIP_STOP"
req.header: 61883.h
req.include-header: 
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
- 61883.h
api_name:
- CIP_STOP
product:
- Windows
targetos: Windows
req.typenames: CIP_STOP, *PCIP_STOP
---

# _CIP_STOP structure


## -description


This structure is used to stop transmission or reception. The  request stops isochronous transmission or reception on the specified connection. This request will stop capturing CIP packets, whether there are any frames attached. If frames are attached and the stream is resumed, then processing of the frame is resumed on the next source packet within the frame. To resume the stream on the beginning of the frame, a driver must set <b>Flags</b> with CIP_RESET_FRAME_ON_DISCONTINUITY in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cip_frame">CIP_FRAME</a> structure passed with AttachFrame request. 


## -struct-fields




### -field hConnect

On input, a handle to the connection on which to stop isochronous transmission or reception.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_INVALID_PARAMETER.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
 

 

