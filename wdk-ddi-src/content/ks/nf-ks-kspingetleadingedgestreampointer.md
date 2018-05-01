---
UID: NF:ks.KsPinGetLeadingEdgeStreamPointer
title: KsPinGetLeadingEdgeStreamPointer function
author: windows-driver-content
description: The KsPinGetLeadingEdgeStreamPointer function acquires the leading edge stream pointer for the queue associated with the given pin.
old-location: stream\kspingetleadingedgestreampointer.htm
old-project: stream
ms.assetid: 05615730-dbeb-496a-b4a8-a16830b31586
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsPinGetLeadingEdgeStreamPointer, KsPinGetLeadingEdgeStreamPointer function [Streaming Media Devices], avfunc_0eb1faec-c090-4647-8306-84cff42ddf9c.xml, ks/KsPinGetLeadingEdgeStreamPointer, stream.kspingetleadingedgestreampointer
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
-	KsPinGetLeadingEdgeStreamPointer
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinGetLeadingEdgeStreamPointer function


## -description


The<b> KsPinGetLeadingEdgeStreamPointer</b> function acquires the leading edge stream pointer for the queue associated with the given pin.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure owning the queue for which the leading edge stream pointer should be acquired.


### -param State [in]

This parameter specifies how to acquire the leading edge stream pointer. Can be one of the following:





#### KSSTREAM_POINTER_STATE_UNLOCKED

Acquire the leading edge stream pointer regardless of whether it references a data frame or not. 

No attempts can be made to access any data associated with the pointer until the pointer is locked. Also note that frames associated with an unlocked stream pointer can be canceled.



#### KSSTREAM_POINTER_STATE_LOCKED

Acquire and lock the leading edge stream pointer. If no data frame is associated with the stream pointer, return <b>NULL</b>. If a non<b>null</b> pointer is returned, it is a locked stream pointer and has a data frame associated with it. Frames associated with a locked stream pointer <b>cannot</b> be canceled. 


## -returns



<b>KsPinGetLeadingEdgeStreamPointer</b> returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure or <b>NULL</b>. A return value of <b>NULL</b> may occur because there is no queue associated with the pin, indicating that the pin does not use the standard transport mechanism. Alternatively, a return value of <b>NULL</b> may occur because an attempt to lock the leading edge failed, indicating that there is no data frame associated with the leading edge.




## -remarks



Filters that implement <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a> often call <b>KsPinGetLeadingEdgeStreamPointer</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563518">KsPinGetTrailingEdgeStreamPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567125">KsStreamPointerAdvance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567127">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892389">KsStreamPointerClone</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567130">KsStreamPointerDelete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892390">KsStreamPointerLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567137">KsStreamPointerUnlock</a>
 

 

