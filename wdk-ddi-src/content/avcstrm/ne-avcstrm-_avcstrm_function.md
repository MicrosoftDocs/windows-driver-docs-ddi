---
UID: NE:avcstrm._AVCSTRM_FUNCTION
title: "_AVCSTRM_FUNCTION"
author: windows-driver-content
description: The AVCSTRM_FUNCTION enumeration defines the functionality exposed by the avcstrm.sys driver.
old-location: stream\avcstrm_function.htm
old-project: stream
ms.assetid: 0dacc4b0-003f-4c73-8705-1c1e86ce357c
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: AVCSTRM_ABORT_STREAMING, AVCSTRM_CLOSE, AVCSTRM_FUNCTION, AVCSTRM_FUNCTION enumeration [Streaming Media Devices], AVCSTRM_GET_PROPERTY, AVCSTRM_GET_STATE, AVCSTRM_OPEN, AVCSTRM_READ, AVCSTRM_SET_PROPERTY, AVCSTRM_SET_STATE, AVCSTRM_WRITE, _AVCSTRM_FUNCTION, avcsref_19b1714d-e3a3-40b8-8dd8-fb17ecb2e777.xml, avcstrm/AVCSTRM_ABORT_STREAMING, avcstrm/AVCSTRM_CLOSE, avcstrm/AVCSTRM_FUNCTION, avcstrm/AVCSTRM_GET_PROPERTY, avcstrm/AVCSTRM_GET_STATE, avcstrm/AVCSTRM_OPEN, avcstrm/AVCSTRM_READ, avcstrm/AVCSTRM_SET_PROPERTY, avcstrm/AVCSTRM_SET_STATE, avcstrm/AVCSTRM_WRITE, stream.avcstrm_function
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
-	avcstrm.h
api_name:
-	AVCSTRM_FUNCTION
product: Windows
targetos: Windows
req.typenames: AVCSTRM_FUNCTION
---

# _AVCSTRM_FUNCTION enumeration


## -description


The AVCSTRM_FUNCTION enumeration defines the functionality exposed by the <i>avcstrm.sys</i> driver.


## -enum-fields




### -field AVCSTRM_READ

Read data from a stream.


### -field AVCSTRM_WRITE

Write data to a stream.


### -field AVCSTRM_ABORT_STREAMING

Abort streaming. This cancels <i>all</i> streaming IRPs. To cancel an individual IRP, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff548338">IoCancelIrp</a>.


### -field AVCSTRM_OPEN

Open a stream in a specific format.


### -field AVCSTRM_CLOSE

Close a stream and free any resources allocated for the stream.


### -field AVCSTRM_GET_STATE

Obtain the stream state.


### -field AVCSTRM_SET_STATE

Place the  stream into a new state.


### -field AVCSTRM_GET_PROPERTY

Get stream property. This function is not implemented.


### -field AVCSTRM_SET_PROPERTY

Set stream property. This function is not implemented.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554107">AVCSTRM_ABORT_STREAMING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554110">AVCSTRM_CLOSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554121">AVCSTRM_GET_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554124">AVCSTRM_GET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554125">AVCSTRM_OPEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554130">AVCSTRM_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554132">AVCSTRM_SET_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554134">AVCSTRM_SET_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554135">AVCSTRM_WRITE</a>
 

 

