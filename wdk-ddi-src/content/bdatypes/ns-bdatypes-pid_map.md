---
UID: NS:bdatypes.PID_MAP
title: PID_MAP
author: windows-driver-content
description: The PID_MAP structure describes a group of packets in the output stream of a packet identifier (PID) filter. This group consists of packets that are identified with an identical PID and contain particular media content.
old-location: stream\pid_map.htm
old-project: stream
ms.assetid: f71045e8-2928-40b8-b8f7-bc954a753aff
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.pid_map, bdaref_54fdf358-1957-4e84-a5a4-9929395f105b.xml, PID_MAP, bdatypes/PID_MAP, PID_MAP structure [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bdatypes.h
apiname:
-	PID_MAP
product: Windows
targetos: Windows
req.typenames: PID_MAP
---

# PID_MAP structure


## -description


The PID_MAP structure describes a group of packets in the output stream of a packet identifier (PID) filter. This group consists of packets that are identified with an identical PID and contain particular media content. 


## -syntax


````
typedef struct {
  ULONG                ulPID;
  MEDIA_SAMPLE_CONTENT MediaSampleContent;
} PID_MAP;
````


## -struct-fields




### -field ulPID

Identifier of particular packets. 


### -field MediaSampleContent

MEDIA_SAMPLE_CONTENT enumerated type value that specifies the type of media content that packets contain. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567719">MEDIA_SAMPLE_CONTENT</a>

<a href="..\bdatypes\ns-bdatypes-_bda_pid_map.md">BDA_PID_MAP</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566551">KSPROPSETID_BdaPIDFilter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PID_MAP structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

