---
UID: NS:netdispumdddi.MIRACAST_CHUNK_INFO
title: MIRACAST_CHUNK_INFO
author: windows-driver-content
description: Contains info about a specified wireless display (Miracast) encode chunk.
old-location: display\miracast_chunk_info.htm
old-project: display
ms.assetid: 7015cbc5-f8d1-4e06-bb02-2706a26877f0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: MIRACAST_CHUNK_INFO structure [Display Devices], netdispumdddi/MIRACAST_CHUNK_INFO, MIRACAST_CHUNK_INFO, display.miracast_chunk_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Netdispumdddi.h
apiname:
-	MIRACAST_CHUNK_INFO
product: Windows
targetos: Windows
req.typenames: MIRACAST_CHUNK_INFO
---

# MIRACAST_CHUNK_INFO structure


## -description


Contains info about a specified wireless display (Miracast) encode chunk.


## -syntax


````
typedef struct {
  MIRACAST_CHUNK_TYPE ChunkType;
  MIRACAST_CHUNK_ID   ChunkId;
  UINT                ProcessingTime;
  UINT                EncodeRate;
} MIRACAST_CHUNK_INFO;
````


## -struct-fields




#### - ChunkType

The type of chunk that is to be processed, specified as a <a href="..\netdispumdddi\ne-netdispumdddi-miracast_chunk_type.md">MIRACAST_CHUNK_TYPE</a> enumeration value.


#### - ChunkId

The identifier for this chunk, of type <a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_id.md">MIRACAST_CHUNK_ID</a>.


#### - ProcessingTime

The time, in microseconds, that it took to process this chunk.


#### - EncodeRate

The encode bit rate, in kilobits per second, that the user-mode driver reported for this chunk.


## -see-also

<a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_id.md">MIRACAST_CHUNK_ID</a>

<a href="..\netdispumdddi\ne-netdispumdddi-miracast_chunk_type.md">MIRACAST_CHUNK_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20MIRACAST_CHUNK_INFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

