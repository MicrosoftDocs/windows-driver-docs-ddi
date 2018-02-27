---
UID: NF:ks.KsStreamPointerDelete
title: KsStreamPointerDelete function
author: windows-driver-content
description: The KsStreamPointerDelete function deletes a clone stream pointer, releasing a reference on the frame to which this stream pointer referred.
old-location: stream\ksstreampointerdelete.htm
old-project: stream
ms.assetid: 68819fe9-fd90-4391-a129-5aa0cae1558b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerDelete, KsStreamPointerDelete function [Streaming Media Devices], avfunc_b21da27c-abf4-4277-8a22-232c31fbfe97.xml, ks/KsStreamPointerDelete, stream.ksstreampointerdelete
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
-	KsStreamPointerDelete
product: Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerDelete function


## -description


The<b> KsStreamPointerDelete </b>function deletes a clone stream pointer, releasing a reference on the frame to which this stream pointer referred.


## -syntax


````
void KsStreamPointerDelete(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the clone stream pointer to delete. Must be a clone stream pointer; cannot be the leading or trailing edge stream pointer.


## -returns



None




## -remarks



If the frame to which <i>StreamPointer</i> points has no other references on it after deletion, it is completed. When the last frame in a given IRP is completed, the IRP is completed.

The leading edge and trailing edge stream pointers for a given queue and pin are special stream pointers that cannot be deleted.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also

<a href="..\ks\nf-ks-kspingetleadingedgestreampointer.md">KsPinGetLeadingEdgeStreamPointer</a>



<a href="..\ks\nf-ks-kspingettrailingedgestreampointer.md">KsPinGetTrailingEdgeStreamPointer</a>



<a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerDelete function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

