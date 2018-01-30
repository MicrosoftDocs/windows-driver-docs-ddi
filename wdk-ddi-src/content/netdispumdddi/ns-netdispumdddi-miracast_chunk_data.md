---
UID: NS:netdispumdddi.MIRACAST_CHUNK_DATA
title: MIRACAST_CHUNK_DATA
author: windows-driver-content
description: Contains encode chunk data that is used when a user-mode driver calls the wireless display (Miracast) GetNextChunkData function.
old-location: display\miracast_chunk_data.htm
old-project: display
ms.assetid: 1ff4af0b-df1c-4529-9f80-c9e44d889a63
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.miracast_chunk_data, netdispumdddi/MIRACAST_CHUNK_DATA, MIRACAST_CHUNK_DATA, MIRACAST_CHUNK_DATA structure [Display Devices]
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
-	MIRACAST_CHUNK_DATA
product: Windows
targetos: Windows
req.typenames: MIRACAST_CHUNK_DATA
---

# MIRACAST_CHUNK_DATA structure


## -description


Contains encode chunk data that is used when a user-mode driver calls the wireless display (Miracast) <a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a> function.


## -syntax


````
typedef struct {
  MIRACAST_CHUNK_INFO ChunkInfo;
  UINT                PrivateDriverDataSize;
  UCHAR               PrivateDriverData[1];
} MIRACAST_CHUNK_DATA;
````


## -struct-fields




### -field ChunkInfo

A <a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_info.md">MIRACAST_CHUNK_INFO</a> encode chunk information structure that the user-mode display driver wants to report.


### -field PrivateDriverDataSize

The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


### -field PrivateDriverData

Private data, of type <b>UCHAR</b>, that the user-mode display driver sends when it calls the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a> function.


## -see-also

<a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_info.md">MIRACAST_CHUNK_INFO</a>

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20MIRACAST_CHUNK_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

