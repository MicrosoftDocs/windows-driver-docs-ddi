---
UID: NS:strmini._STREAM_DATA_INTERSECT_INFO
title: "_STREAM_DATA_INTERSECT_INFO"
author: windows-driver-content
description: STREAM_DATA_INTERSECT_INFO describes the parameters of a data intersection operation.
old-location: stream\stream_data_intersect_info.htm
old-project: stream
ms.assetid: 92a37945-4b7c-4d10-a071-ae1584590692
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: strmini/STREAM_DATA_INTERSECT_INFO, strmini/PSTREAM_DATA_INTERSECT_INFO, PSTREAM_DATA_INTERSECT_INFO, stream.stream_data_intersect_info, STREAM_DATA_INTERSECT_INFO, strclass-struct_28443f9e-3daf-4a83-be5e-de1868590510.xml, *PSTREAM_DATA_INTERSECT_INFO, _STREAM_DATA_INTERSECT_INFO, STREAM_DATA_INTERSECT_INFO structure [Streaming Media Devices], PSTREAM_DATA_INTERSECT_INFO structure pointer [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	strmini.h
apiname:
-	STREAM_DATA_INTERSECT_INFO
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_DATA_INTERSECT_INFO, STREAM_DATA_INTERSECT_INFO"
req.product: Windows 10 or later.
---

# _STREAM_DATA_INTERSECT_INFO structure


## -description


STREAM_DATA_INTERSECT_INFO describes the parameters of a data intersection operation.


## -syntax


````
typedef struct _STREAM_DATA_INTERSECT_INFO {
  ULONG        StreamNumber;
  PKSDATARANGE DataRange;
  PVOID        DataFormatBuffer;
  ULONG        SizeOfDataFormatBuffer;
} STREAM_DATA_INTERSECT_INFO, *PSTREAM_DATA_INTERSECT_INFO;
````


## -struct-fields




### -field StreamNumber

Specifies the stream number. This corresponds to the offset of the stream within the minidriver's array of <a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a> structures. The possible data formats depend on the stream type.


### -field DataRange

Pointer to the data ranges to be examined for a match.


### -field DataFormatBuffer

Pointer to the buffer the minidriver fills in with the matching data format.


### -field SizeOfDataFormatBuffer

Specifies the size in bytes of the <b>DataFormatBuffer</b>.


## -remarks


The class driver passes this data structure when it submits a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568168">SRB_GET_DATA_INTERSECTION</a> request to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a>.


