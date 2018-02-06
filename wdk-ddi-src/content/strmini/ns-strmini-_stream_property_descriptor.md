---
UID: NS:strmini._STREAM_PROPERTY_DESCRIPTOR
title: "_STREAM_PROPERTY_DESCRIPTOR"
author: windows-driver-content
description: STREAM_PROPERTY_DESCRIPTOR specifies the parameters of property get/set requests that the class driver passes to the minidriver.
old-location: stream\stream_property_descriptor.htm
old-project: stream
ms.assetid: b72265b7-dce3-4688-bee7-2a6f7d7731f9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.stream_property_descriptor, strmini/PSTREAM_PROPERTY_DESCRIPTOR, *PSTREAM_PROPERTY_DESCRIPTOR, strclass-struct_5cf57d2b-c4ea-41fb-b3b3-4b6f67c2ecca.xml, _STREAM_PROPERTY_DESCRIPTOR, STREAM_PROPERTY_DESCRIPTOR, PSTREAM_PROPERTY_DESCRIPTOR, PSTREAM_PROPERTY_DESCRIPTOR structure pointer [Streaming Media Devices], STREAM_PROPERTY_DESCRIPTOR structure [Streaming Media Devices], strmini/STREAM_PROPERTY_DESCRIPTOR
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
-	STREAM_PROPERTY_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STREAM_PROPERTY_DESCRIPTOR, *PSTREAM_PROPERTY_DESCRIPTOR
req.product: Windows 10 or later.
---

# _STREAM_PROPERTY_DESCRIPTOR structure


## -description


STREAM_PROPERTY_DESCRIPTOR specifies the parameters of property get/set requests that the class driver passes to the minidriver.


## -syntax


````
typedef struct _STREAM_PROPERTY_DESCRIPTOR {
  PKSPROPERTY Property;
  ULONG       PropertySetID;
  PVOID       PropertyInfo;
  ULONG       PropertyInputSize;
  ULONG       PropertyOutputSize;
} STREAM_PROPERTY_DESCRIPTOR, *PSTREAM_PROPERTY_DESCRIPTOR;
````


## -struct-fields




### -field Property

Specifies the property to be read/written.


### -field PropertySetID

Specifies the index of the property set within either the <a href="..\strmini\ns-strmini-_hw_stream_header.md">HW_STREAM_HEADER</a>'s <b>DevicePropertiesArray</b> (for minidriver properties) or the <a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a>'s <b>StreamPropertiesArray</b> (for stream properties).


### -field PropertyInfo

Points to a buffer that the property data will be read from or written to.


### -field PropertyInputSize

Size of the <b>Property</b> buffer.


### -field PropertyOutputSize

Size of the <b>PropertyInfo</b> buffer.

