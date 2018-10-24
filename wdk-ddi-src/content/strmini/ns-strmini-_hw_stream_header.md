---
UID: NS:strmini._HW_STREAM_HEADER
title: "_HW_STREAM_HEADER"
author: windows-driver-content
description: The HW_STREAM_HEADER structure describes the kernel streaming semantics supported by the minidriver as a whole, as part of a HW_STREAM_DESCRIPTOR structure.
old-location: stream\hw_stream_header.htm
tech.root: stream
ms.assetid: 1931c640-666b-4db5-8d05-eab43ae96665
ms.date: 04/23/2018
ms.keywords: "*PHW_STREAM_HEADER, HW_STREAM_HEADER, HW_STREAM_HEADER structure [Streaming Media Devices], PHW_STREAM_HEADER, PHW_STREAM_HEADER structure pointer [Streaming Media Devices], _HW_STREAM_HEADER, strclass-struct_bf41c526-276a-4e94-9d27-97177a3164bc.xml, stream.hw_stream_header, strmini/HW_STREAM_HEADER, strmini/PHW_STREAM_HEADER"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	strmini.h
api_name:
-	HW_STREAM_HEADER
product:
- Windows
targetos: Windows
req.typenames: HW_STREAM_HEADER, *PHW_STREAM_HEADER
---

# _HW_STREAM_HEADER structure


## -description


The HW_STREAM_HEADER structure describes the kernel streaming semantics supported by the minidriver as a whole, as part of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559686">HW_STREAM_DESCRIPTOR</a> structure.


## -struct-fields




### -field NumberOfStreams

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559692">HW_STREAM_INFORMATION</a> structures that follow this header.


### -field SizeOfHwStreamInformation

The size, in bytes, of the HW_STREAM_INFORMATION structure.


### -field NumDevPropArrayEntries

The number of entries in the array pointed to by <b>DevicePropertiesArray</b>.


### -field DevicePropertiesArray

Pointer to the beginning of the array of property sets that the minidriver as a whole supports. (Property sets supported by individual streams can be found in the <b>StreamPropertiesArray</b> member of the stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559692">HW_STREAM_INFORMATION</a> structure.)


### -field NumDevEventArrayEntries

The number of entries in the array pointed to by <b>DeviceEventsArray</b>.


### -field DeviceEventsArray

Pointer to the beginning of the array of event sets supported by the minidriver.


### -field Topology

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567146">KSTOPOLOGY</a> structure that describes the minidriver's internal topology of nodes and pins. The class driver uses this to handle the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566598">KSPROPSETID_Topology</a> property set for the minidriver.


### -field DeviceEventRoutine

Points to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568457">StrMiniEvent</a> routine.


### -field NumDevMethodArrayEntries

 


### -field DeviceMethodsArray

 


### -field Reserved

Reserved for system use. Do not use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559686">HW_STREAM_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559692">HW_STREAM_INFORMATION</a>
 

 

