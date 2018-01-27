---
UID: NS:61883._CIP_VALIDATE_INFO
title: _CIP_VALIDATE_INFO
author: windows-driver-content
description: The CIP_VALIDATE_INFO structure contains information about the frame.
old-location: ieee\cip_validate_info.htm
old-project: IEEE
ms.assetid: 98993973-91a4-456a-9343-c744408055ed
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PCIP_VALIDATE_INFO structure pointer [Buses], PCIP_VALIDATE_INFO, IEEE.cip_validate_info, 61883/CIP_VALIDATE_INFO, CIP_VALIDATE_INFO, _CIP_VALIDATE_INFO, *PCIP_VALIDATE_INFO, 61883/PCIP_VALIDATE_INFO, CIP_VALIDATE_INFO structure [Buses], 61883_structures_9f8bc3f2-ad43-4e0b-a4f9-8d441397f11d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	61883.h
apiname: 
-	CIP_VALIDATE_INFO
product: Windows
targetos: Windows
req.typenames: *PCIP_VALIDATE_INFO, CIP_VALIDATE_INFO
---

# _CIP_VALIDATE_INFO structure


## -description


The CIP_VALIDATE_INFO structure contains information about the frame. 


## -syntax


````
typedef struct _CIP_VALIDATE_INFO {
  HANDLE     hConnect;
  PVOID      Context;
  CYCLE_TIME TimeStamp;
  PUCHAR     Packet;
} CIP_VALIDATE_INFO, *PCIP_VALIDATE_INFO;
````


## -struct-fields




### -field hConnect

A handle to the connection.


### -field Context

Points to the context provided by the caller at <b>ValidateContext</b> in the input CIP_FRAME structure.


### -field TimeStamp

The timestamp of the current source packet.


### -field Packet

The packet offset for the current source packet.


## -remarks


The IEC-61883 protocol driver allocates and initializes this structure from the input CIP_FRAME structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537045">CIP_FRAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CIP_VALIDATE_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

