---
UID: NS:strmini._HW_STREAM_HEADER
title: "_HW_STREAM_HEADER"
author: windows-driver-content
description: The HW_STREAM_HEADER structure describes the kernel streaming semantics supported by the minidriver as a whole, as part of a HW_STREAM_DESCRIPTOR structure.
old-location: stream\hw_stream_header.htm
old-project: stream
ms.assetid: 1931c640-666b-4db5-8d05-eab43ae96665
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PHW_STREAM_HEADER, ,, A, D, E, H, HW_STREAM_HEADER, HW_STREAM_HEADER structure [Streaming Media Devices], M, P, PHW_STREAM_HEADER, PHW_STREAM_HEADER structure pointer [Streaming Media Devices], R, S, T, W, _, _HW_STREAM_HEADER, strclass-struct_bf41c526-276a-4e94-9d27-97177a3164bc.xml, stream.hw_stream_header, strmini/HW_STREAM_HEADER, strmini/PHW_STREAM_HEADER"
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
-	HW_STREAM_HEADER
product: Windows
targetos: Windows
req.typenames: HW_STREAM_HEADER, *PHW_STREAM_HEADER
req.product: Windows 10 or later.
---

# _HW_STREAM_HEADER structure


## -description


The HW_STREAM_HEADER structure describes the kernel streaming semantics supported by the minidriver as a whole, as part of a <a href="..\strmini\ns-strmini-_hw_stream_descriptor.md">HW_STREAM_DESCRIPTOR</a> structure.


## -syntax


````
typedef struct _HW_STREAM_HEADER {
  ULONG             NumberOfStreams;
  ULONG             SizeOfHwStreamInformation;
  ULONG             NumDevPropArrayEntries;
  PKSPROPERTY_SET   DevicePropertiesArray;
  ULONG             NumDevEventArrayEntries;
  PKSEVENT_SET      DeviceEventsArray;
  PKSTOPOLOGY       Topology;
  PHW_EVENT_ROUTINE DeviceEventRoutine;
  ULONG             Reserved[2];
} HW_STREAM_HEADER, *PHW_STREAM_HEADER;
````


## -struct-fields




### -field NumberOfStreams

The number of <a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a> structures that follow this header.


### -field SizeOfHwStreamInformation

The size, in bytes, of the HW_STREAM_INFORMATION structure.


### -field NumDevPropArrayEntries

The number of entries in the array pointed to by <b>DevicePropertiesArray</b>.


### -field DevicePropertiesArray

Pointer to the beginning of the array of property sets that the minidriver as a whole supports. (Property sets supported by individual streams can be found in the <b>StreamPropertiesArray</b> member of the stream's <a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a> structure.)


### -field NumDevEventArrayEntries

The number of entries in the array pointed to by <b>DeviceEventsArray</b>.


### -field DeviceEventsArray

Pointer to the beginning of the array of event sets supported by the minidriver.


### -field Topology

Pointer to the <a href="..\ks\ns-ks-kstopology.md">KSTOPOLOGY</a> structure that describes the minidriver's internal topology of nodes and pins. The class driver uses this to handle the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566598">KSPROPSETID_Topology</a> property set for the minidriver.


### -field DeviceEventRoutine

Points to the minidriver's <a href="..\strmini\nc-strmini-phw_event_routine.md">StrMiniEvent</a> routine.


### -field NumDevMethodArrayEntries

 


### -field DeviceMethodsArray

 


### -field Reserved

Reserved for system use. Do not use.


## -see-also

<a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a>



<a href="..\strmini\ns-strmini-_hw_stream_descriptor.md">HW_STREAM_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20HW_STREAM_HEADER structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

