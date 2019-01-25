---
UID: NF:ks.KsStreamPointerClone
title: KsStreamPointerClone function (ks.h)
description: The KsStreamPointerClone function creates a clone of a given stream pointer.
old-location: stream\ksstreampointerclone.htm
tech.root: stream
ms.assetid: b51e1c17-e6b5-4108-bfbc-29f1ee06d9f4
ms.date: 04/23/2018
ms.keywords: KsStreamPointerClone, KsStreamPointerClone function [Streaming Media Devices], avfunc_29a7da58-5321-4c19-83df-c9deab062e78.xml, ks/KsStreamPointerClone, stream.ksstreampointerclone
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
-	KsStreamPointerClone
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerClone function


## -description


The<b> KsStreamPointerClone </b>function creates a clone of a given stream pointer.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure representing the stream pointer that is to be cloned.


### -param CancelCallback [in, optional]

Optional. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554271">AVStrMiniCancelCallback</a> routine. AVStream calls this routine if the IRP associated with <i>CloneStreamPointer</i> is canceled.


### -param ContextSize [in]

This parameter indicates how many bytes of minidriver context information the resulting clone stream pointer should have. If nonzero, the requested number of bytes are allocated immediately after the returned stream pointer, and the <i>Context</i> field of <i>CloneStreamPointer</i> points to the allocated memory.


### -param CloneStreamPointer [out]

A pointer to a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure. Upon successful completion of the cloning operation, <i>CloneStreamPointer</i> contains a pointer to the address of the cloned stream pointer.


## -returns



<b>KsStreamPointerClone </b>returns either STATUS_SUCCESS, indicating that the cloning operation completed normally, or an appropriate error code.




## -remarks



The resulting clone initially refers to the same data frame as the original stream pointer and is in the same state (locked or unlocked). Adding a clone stream pointer referencing a data frame increments the reference count on that particular frame. Note that the frame in question, and therefore the IRP to which the frame belongs, is not completed until the reference count drops to zero.

You can use the <i>ContextSize</i> parameter of this call to minimize allocation calls.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567125">KsStreamPointerAdvance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567126">KsStreamPointerAdvanceOffsets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567127">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567130">KsStreamPointerDelete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892390">KsStreamPointerLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567137">KsStreamPointerUnlock</a>
 

 

