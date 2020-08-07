---
UID: NS:61883._CIP_NOTIFY_INFO
title: _CIP_NOTIFY_INFO (61883.h)
description: The CIP_NOTIFY_INFO structure contains information about the frame.
old-location: ieee\cip_notify_info.htm
tech.root: IEEE
ms.assetid: 60b0d44b-0178-43ce-a1ad-7f5825bed3ba
ms.date: 02/15/2018
keywords: ["CIP_NOTIFY_INFO structure"]
ms.keywords: "*PCIP_NOTIFY_INFO, 61883/CIP_NOTIFY_INFO, 61883/PCIP_NOTIFY_INFO, 61883_structures_383bc74c-1168-4478-8284-b2724f9ec654.xml, CIP_NOTIFY_INFO, CIP_NOTIFY_INFO structure [Buses], IEEE.cip_notify_info, PCIP_NOTIFY_INFO, PCIP_NOTIFY_INFO structure pointer [Buses], _CIP_NOTIFY_INFO"
f1_keywords:
 - "61883/CIP_NOTIFY_INFO"
 - "CIP_NOTIFY_INFO"
req.header: 61883.h
req.include-header: 61883.h
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
- CIP_NOTIFY_INFO
targetos: Windows
req.typenames: CIP_NOTIFY_INFO, *PCIP_NOTIFY_INFO
---

# _CIP_NOTIFY_INFO structure


## -description


The CIP_NOTIFY_INFO structure contains information about the frame. 


## -struct-fields




### -field hConnect

A handle to the connection.


### -field Context

Points to the context provided by the caller at <b>NotifyContext</b> in the input CIP_FRAME structure.


### -field Frame

Points to the completed frame.


## -remarks



The IEC-61883 protocol driver allocates and initializes this structure from the input CIP_FRAME structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cip_frame">CIP_FRAME</a>
 

 

