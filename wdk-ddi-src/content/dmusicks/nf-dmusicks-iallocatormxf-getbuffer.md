---
UID: NF:dmusicks.IAllocatorMXF.GetBuffer
title: IAllocatorMXF::GetBuffer method
author: windows-driver-content
description: The GetBuffer method allocates a buffer for long MIDI events.
old-location: audio\iallocatormxf_getbuffer.htm
old-project: audio
ms.assetid: eebae465-a49a-4e19-a636-9da7f9db7278
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audmp-routines_5abb78f4-de92-4342-877f-e7f1c15f8d8e.xml, dmusicks/IAllocatorMXF::GetBuffer, audio.iallocatormxf_getbuffer, GetBuffer method [Audio Devices], IAllocatorMXF, IAllocatorMXF::GetBuffer, IAllocatorMXF interface [Audio Devices], GetBuffer method, GetBuffer, GetBuffer method [Audio Devices], IAllocatorMXF interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
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
req.lib: dmusicks.h
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dmusicks.h
apiname:
-	IAllocatorMXF.GetBuffer
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IAllocatorMXF::GetBuffer method


## -description


The <code>GetBuffer</code> method allocates a buffer for long MIDI events.


## -syntax


````
NTSTATUS GetBuffer(
  [out] PBYTE *ppbBuffer
);
````


## -parameters




### -param ppBuffer





#### - ppbBuffer [out]

Output pointer for the buffer. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the buffer.


## -returns


<code>GetBuffer</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.



## -remarks


The miniport driver calls this method only when it needs to send large chunks of data to the capture sink. Specifically, the miniport driver uses this method whenever a component needs to package more data than can be stored in the <b>uData</b> member of <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a>.

The size of the buffer can determined by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff536493">IAllocatorMXF::GetBufferSize</a>. <code>GetBufferSize</code> needs to be called only once because the buffer size is constant for any allocator implementation.



## -see-also

<a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a>

<a href="..\dmusicks\nn-dmusicks-iallocatormxf.md">IAllocatorMXF</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536493">IAllocatorMXF::GetBufferSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAllocatorMXF::GetBuffer method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

