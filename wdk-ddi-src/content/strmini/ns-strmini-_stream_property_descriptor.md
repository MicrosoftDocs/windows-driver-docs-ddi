---
UID: NS:strmini._STREAM_PROPERTY_DESCRIPTOR
title: _STREAM_PROPERTY_DESCRIPTOR (strmini.h)
description: STREAM_PROPERTY_DESCRIPTOR specifies the parameters of property get/set requests that the class driver passes to the minidriver.
old-location: stream\stream_property_descriptor.htm
tech.root: stream
ms.assetid: b72265b7-dce3-4688-bee7-2a6f7d7731f9
ms.date: 04/23/2018
keywords: ["_STREAM_PROPERTY_DESCRIPTOR structure"]
ms.keywords: "*PSTREAM_PROPERTY_DESCRIPTOR, PSTREAM_PROPERTY_DESCRIPTOR, PSTREAM_PROPERTY_DESCRIPTOR structure pointer [Streaming Media Devices], STREAM_PROPERTY_DESCRIPTOR, STREAM_PROPERTY_DESCRIPTOR structure [Streaming Media Devices], _STREAM_PROPERTY_DESCRIPTOR, strclass-struct_5cf57d2b-c4ea-41fb-b3b3-4b6f67c2ecca.xml, stream.stream_property_descriptor, strmini/PSTREAM_PROPERTY_DESCRIPTOR, strmini/STREAM_PROPERTY_DESCRIPTOR"
f1_keywords:
 - "strmini/STREAM_PROPERTY_DESCRIPTOR"
 - "STREAM_PROPERTY_DESCRIPTOR"
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
- STREAM_PROPERTY_DESCRIPTOR
targetos: Windows
req.typenames: STREAM_PROPERTY_DESCRIPTOR, *PSTREAM_PROPERTY_DESCRIPTOR
---

# _STREAM_PROPERTY_DESCRIPTOR structure


## -description


STREAM_PROPERTY_DESCRIPTOR specifies the parameters of property get/set requests that the class driver passes to the minidriver.


## -struct-fields




### -field Property

Specifies the property to be read/written.


### -field PropertySetID

Specifies the index of the property set within either the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_header">HW_STREAM_HEADER</a>'s <b>DevicePropertiesArray</b> (for minidriver properties) or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_information">HW_STREAM_INFORMATION</a>'s <b>StreamPropertiesArray</b> (for stream properties).


### -field PropertyInfo

Points to a buffer that the property data will be read from or written to.


### -field PropertyInputSize

Size of the <b>Property</b> buffer.


### -field PropertyOutputSize

Size of the <b>PropertyInfo</b> buffer.

