---
UID: NF:ks.KsStreamPointerClone
title: KsStreamPointerClone function
author: windows-driver-content
description: The KsStreamPointerClone function creates a clone of a given stream pointer.
old-location: stream\ksstreampointerclone.htm
old-project: stream
ms.assetid: b51e1c17-e6b5-4108-bfbc-29f1ee06d9f4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsStreamPointerClone, ks/KsStreamPointerClone, stream.ksstreampointerclone, KsStreamPointerClone function [Streaming Media Devices], avfunc_29a7da58-5321-4c19-83df-c9deab062e78.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsStreamPointerClone
product: Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerClone function


## -description


The<b> KsStreamPointerClone </b>function creates a clone of a given stream pointer.


## -syntax


````
NTSTATUS KsStreamPointerClone(
  _In_     PKSSTREAM_POINTER  StreamPointer,
  _In_opt_ PFNKSSTREAMPOINTER CancelCallback,
  _In_     ULONG              ContextSize,
  _Out_    PKSSTREAM_POINTER  *CloneStreamPointer
);
````


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the stream pointer that is to be cloned.


### -param CancelCallback [in, optional]

Optional. A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnksstreampointer.md">AVStrMiniCancelCallback</a> routine. AVStream calls this routine if the IRP associated with <i>CloneStreamPointer</i> is canceled.


### -param ContextSize [in]

This parameter indicates how many bytes of minidriver context information the resulting clone stream pointer should have. If nonzero, the requested number of bytes are allocated immediately after the returned stream pointer, and the <i>Context</i> field of <i>CloneStreamPointer</i> points to the allocated memory.


### -param CloneStreamPointer [out]

A pointer to a pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure. Upon successful completion of the cloning operation, <i>CloneStreamPointer</i> contains a pointer to the address of the cloned stream pointer.


## -returns


<b>KsStreamPointerClone </b>returns either STATUS_SUCCESS, indicating that the cloning operation completed normally, or an appropriate error code.



## -remarks


The resulting clone initially refers to the same data frame as the original stream pointer and is in the same state (locked or unlocked). Adding a clone stream pointer referencing a data frame increments the reference count on that particular frame. Note that the frame in question, and therefore the IRP to which the frame belongs, is not completed until the reference count drops to zero.

You can use the <i>ContextSize</i> parameter of this call to minimize allocation calls.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.



## -see-also

<a href="..\ks\nf-ks-ksstreampointeradvanceoffsets.md">KsStreamPointerAdvanceOffsets</a>

<a href="..\ks\nf-ks-ksstreampointerunlock.md">KsStreamPointerUnlock</a>

<a href="..\ks\nf-ks-ksstreampointerdelete.md">KsStreamPointerDelete</a>

<a href="..\ks\nf-ks-ksstreampointeradvanceoffsetsandunlock.md">KsStreamPointerAdvanceOffsetsAndUnlock</a>

<a href="..\ks\nf-ks-ksstreampointerlock.md">KsStreamPointerLock</a>

<a href="..\ks\nf-ks-ksstreampointeradvance.md">KsStreamPointerAdvance</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerClone function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

