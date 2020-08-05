---
UID: NS:strmini._STREAM_DATA_INTERSECT_INFO
title: _STREAM_DATA_INTERSECT_INFO (strmini.h)
description: STREAM_DATA_INTERSECT_INFO describes the parameters of a data intersection operation.
old-location: stream\stream_data_intersect_info.htm
tech.root: stream
ms.assetid: 92a37945-4b7c-4d10-a071-ae1584590692
ms.date: 04/23/2018
keywords: ["STREAM_DATA_INTERSECT_INFO structure"]
ms.keywords: "*PSTREAM_DATA_INTERSECT_INFO, PSTREAM_DATA_INTERSECT_INFO, PSTREAM_DATA_INTERSECT_INFO structure pointer [Streaming Media Devices], STREAM_DATA_INTERSECT_INFO, STREAM_DATA_INTERSECT_INFO structure [Streaming Media Devices], _STREAM_DATA_INTERSECT_INFO, strclass-struct_28443f9e-3daf-4a83-be5e-de1868590510.xml, stream.stream_data_intersect_info, strmini/PSTREAM_DATA_INTERSECT_INFO, strmini/STREAM_DATA_INTERSECT_INFO"
f1_keywords:
 - "strmini/STREAM_DATA_INTERSECT_INFO"
 - "STREAM_DATA_INTERSECT_INFO"
req.header: strmini.h
req.include-header: Strmini.h
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
- strmini.h
api_name:
- STREAM_DATA_INTERSECT_INFO
targetos: Windows
req.typenames: STREAM_DATA_INTERSECT_INFO, *PSTREAM_DATA_INTERSECT_INFO
---

# _STREAM_DATA_INTERSECT_INFO structure


## -description


STREAM_DATA_INTERSECT_INFO describes the parameters of a data intersection operation.


## -struct-fields




### -field StreamNumber

Specifies the stream number. This corresponds to the offset of the stream within the minidriver's array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_information">HW_STREAM_INFORMATION</a> structures. The possible data formats depend on the stream type.


### -field DataRange

Pointer to the data ranges to be examined for a match.


### -field DataFormatBuffer

Pointer to the buffer the minidriver fills in with the matching data format.


### -field SizeOfDataFormatBuffer

Specifies the size in bytes of the <b>DataFormatBuffer</b>.


## -remarks



The class driver passes this data structure when it submits a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-get-data-intersection">SRB_GET_DATA_INTERSECTION</a> request to the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveDevicePacket</a>.



