---
UID: NF:ks.KsPinSubmitFrameMdl
title: KsPinSubmitFrameMdl function
author: windows-driver-content
description: If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrameMdl function submits a frame directly into the transport circuit.
old-location: stream\kspinsubmitframemdl.htm
tech.root: stream
ms.assetid: 8033c0a9-86dd-4d54-b93e-66c926cae952
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsPinSubmitFrameMdl, KsPinSubmitFrameMdl function [Streaming Media Devices], avfunc_456aa5db-b749-4b95-8448-f024dbc2030b.xml, ks/KsPinSubmitFrameMdl, stream.kspinsubmitframemdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsPinSubmitFrameMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinSubmitFrameMdl function


## -description


If a pin has been placed into injection mode by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff563522">KsPinRegisterFrameReturnCallback</a>, the <b>KsPinSubmitFrameMdl</b> function submits a frame directly into the transport circuit.


## -parameters




### -param Pin [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure representing the pin on which to submit a frame.


### -param Mdl [in, optional]

A pointer to a memory descriptor list describing the frame buffer. Optional.


### -param StreamHeader [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a> structure. The stream header is copied if this parameter is supplied. Optional.


### -param Context [in, optional]

A pointer to a caller-allocated buffer that is passed to the frame return callback registered through <a href="https://msdn.microsoft.com/library/windows/hardware/ff563522">KsPinRegisterFrameReturnCallback</a>. This parameter is optional and is solely for the caller's use.


## -returns



Returns STATUS_SUCCESS if frame submission is successful. Otherwise returns an appropriate error code.




## -remarks



The difference between this function and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563529">KsPinSubmitFrame</a> is that this function will submit a frame using an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> structure rather than a data and size argument.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563522">KsPinRegisterFrameReturnCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563529">KsPinSubmitFrame</a>
 

 

