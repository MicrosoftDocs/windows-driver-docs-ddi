---
UID: NE:ks.PKSPIN_DATAFLOW
title: "*PKSPIN_DATAFLOW"
author: windows-driver-content
description: An instance of the KSPIN_DATAFLOW enumeration is returned by KSPROPERTY_PIN_DATAFLOW.
old-location: stream\kspin_dataflow.htm
old-project: stream
ms.assetid: feab830d-8079-4051-8974-52905f845765
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PKSPIN_DATAFLOW enumeration pointer [Streaming Media Devices], *PKSPIN_DATAFLOW, ks/PKSPIN_DATAFLOW, KSPIN_DATAFLOW_OUT, KSPIN_DATAFLOW_IN, KSPIN_DATAFLOW, KSPIN_DATAFLOW enumeration [Streaming Media Devices], ks/KSPIN_DATAFLOW, stream.kspin_dataflow, PKSPIN_DATAFLOW, ks-struct_2161b89b-ba7c-440a-9006-c3445b392b89.xml, ks/KSPIN_DATAFLOW_OUT, ks/KSPIN_DATAFLOW_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSPIN_DATAFLOW
product: Windows
targetos: Windows
req.typenames: KSPIN_DATAFLOW, *PKSPIN_DATAFLOW
---

# *PKSPIN_DATAFLOW enumeration


## -description


An instance of the KSPIN_DATAFLOW enumeration is returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff565197">KSPROPERTY_PIN_DATAFLOW</a>.


## -syntax


````
typedef enum  { 
  KSPIN_DATAFLOW_IN   = 1,
  KSPIN_DATAFLOW_OUT  = 2
} KSPIN_DATAFLOW, *PKSPIN_DATAFLOW;
````


## -enum-fields




### -field KSPIN_DATAFLOW_IN

Indicates that the pin factory instantiates data sink pins. Such pins can only be connected to data source pins. 


### -field KSPIN_DATAFLOW_OUT

Indicates that the pin factory instantiates data source pins. Such pins can only be connected to data sink pins.


## -see-also

<a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



<a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPIN_DATAFLOW enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

