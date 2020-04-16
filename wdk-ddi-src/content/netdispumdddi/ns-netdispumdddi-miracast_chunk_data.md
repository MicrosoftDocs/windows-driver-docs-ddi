---
UID: NS:netdispumdddi.__unnamed_struct_3
title: MIRACAST_CHUNK_DATA (netdispumdddi.h)
description: Contains encode chunk data that is used when a user-mode driver calls the wireless display (Miracast) GetNextChunkData function.
old-location: display\miracast_chunk_data.htm
tech.root: display
ms.assetid: 1ff4af0b-df1c-4529-9f80-c9e44d889a63
ms.date: 05/10/2018
keywords: ["MIRACAST_CHUNK_DATA structure"]
ms.keywords: MIRACAST_CHUNK_DATA, MIRACAST_CHUNK_DATA structure [Display Devices], display.miracast_chunk_data, netdispumdddi/MIRACAST_CHUNK_DATA
f1_keywords:
 - "netdispumdddi/MIRACAST_CHUNK_DATA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Netdispumdddi.h
api_name:
- MIRACAST_CHUNK_DATA
product:
- Windows
targetos: Windows
req.typenames: MIRACAST_CHUNK_DATA
---

# MIRACAST_CHUNK_DATA structure


## -description


Contains encode chunk data that is used when a user-mode driver calls the wireless display (Miracast) <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_get_next_chunk_data">GetNextChunkData</a> function.


## -struct-fields




### -field ChunkInfo

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_chunk_info">MIRACAST_CHUNK_INFO</a> encode chunk information structure that the user-mode display driver wants to report.


### -field PrivateDriverDataSize

The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


### -field PrivateDriverData

Private data, of type <b>UCHAR</b>, that the user-mode display driver sends when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_get_next_chunk_data">GetNextChunkData</a> function.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_get_next_chunk_data">GetNextChunkData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_chunk_info">MIRACAST_CHUNK_INFO</a>
 

 

