---
UID: NS:61883._CIP_ATTACH_FRAME
title: "_CIP_ATTACH_FRAME"
author: windows-driver-content
description: This structure is used in an attach frame request.
old-location: ieee\cip_attach_frame.htm
old-project: IEEE
ms.assetid: F7E283BB-B714-4CD4-AFF4-EFB62D82791D
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCIP_ATTACH_FRAME, 61883/CIP_ATTACH_FRAME, 61883/PCIP_ATTACH_FRAME, CIP_ATTACH_FRAME, CIP_ATTACH_FRAME structure [Buses], IEEE.cip_attach_frame, PCIP_ATTACH_FRAME, PCIP_ATTACH_FRAME structure pointer [Buses], _CIP_ATTACH_FRAME"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	CIP_ATTACH_FRAME
product: Windows
targetos: Windows
req.typenames: CIP_ATTACH_FRAME, *PCIP_ATTACH_FRAME
---

# _CIP_ATTACH_FRAME structure


## -description


This structure is used in an attach frame request. The  request attaches a frame buffer to the specified plug for a subsequent Talk or Listen request. The IEC-61883 protocol driver subdivides the frames into source packets and blocks. By default, the timestamp returned is the time at completion of the frame transmission. 


## -struct-fields




### -field hConnect

A handle to the connection.


### -field FrameLength

The length of the frame in bytes. The total frame length must be evenly divisible by the value in <b>SourceLength</b>.


### -field SourceLength

The length of the source packets, in bytes. The source length must be evenly divisible into the frame length.


### -field Frame

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537045">CIP_FRAME</a> structure that contains information about the frame and a data buffer to be sent or filled.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_INSUFFICIENT_RESOURCES.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

