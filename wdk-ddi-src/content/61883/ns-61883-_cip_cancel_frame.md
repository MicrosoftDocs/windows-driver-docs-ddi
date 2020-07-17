---
UID: NS:61883._CIP_CANCEL_FRAME
title: _CIP_CANCEL_FRAME (61883.h)
description: The request cancels an attached frame buffer. A frame can be canceled while the stream is running.
old-location: ieee\cip_cancel_frame.htm
tech.root: IEEE
ms.assetid: 952625D0-BA82-40C1-8EBF-8CD54C0E4C40
ms.date: 02/15/2018
keywords: ["_CIP_CANCEL_FRAME structure"]
ms.keywords: "*PCIP_CANCEL_FRAME, 61883/CIP_CANCEL_FRAME, 61883/PCIP_CANCEL_FRAME, CIP_CANCEL_FRAME, CIP_CANCEL_FRAME structure [Buses], IEEE.cip_cancel_frame, PCIP_CANCEL_FRAME, PCIP_CANCEL_FRAME structure pointer [Buses], _CIP_CANCEL_FRAME"
f1_keywords:
 - "61883/CIP_CANCEL_FRAME"
 - "CIP_CANCEL_FRAME"
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
- CIP_CANCEL_FRAME
product:
- Windows
targetos: Windows
req.typenames: CIP_CANCEL_FRAME, *PCIP_CANCEL_FRAME
---

# _CIP_CANCEL_FRAME structure


## -description


This structure is the input buffer in a cancel frame request. The request cancels an attached frame buffer. A frame can be canceled while the stream is running. If the canceled frame has already been sent, the protocol driver sets a status of STATUS_NOT_FOUND.


## -struct-fields




### -field hConnect

A handle to a connection.


### -field Frame

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cip_frame">CIP_FRAME</a> structure that contains information about the frame to cancel.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
 

 

