---
UID: NF:dmusicks.IAllocatorMXF.PutBuffer
title: IAllocatorMXF::PutBuffer method
author: windows-driver-content
description: This method is not currently used by the miniport driver. The PutBuffer method passes a buffer to the allocator, but this occurs automatically when IMXF::PutMessage is called anyway.
old-location: audio\iallocatormxf_putbuffer.htm
old-project: audio
ms.assetid: 20daf292-9476-4435-915d-f97fba3a6ec2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IAllocatorMXF, IAllocatorMXF interface [Audio Devices], PutBuffer method, IAllocatorMXF::PutBuffer, PutBuffer method [Audio Devices], PutBuffer method [Audio Devices], IAllocatorMXF interface, PutBuffer,IAllocatorMXF.PutBuffer, audio.iallocatormxf_putbuffer, audmp-routines_8afbc000-69b1-45a5-8fe3-3f6ff8d5518d.xml, dmusicks/IAllocatorMXF::PutBuffer
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	IAllocatorMXF.PutBuffer
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IAllocatorMXF::PutBuffer method


## -description



   This method is not currently used by the miniport driver. The <code>PutBuffer</code> method passes a buffer to the allocator, but this occurs automatically when <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a> is called anyway.


## -syntax


````
NTSTATUS PutBuffer(
  [in] PBYTE pbBuffer
);
````


## -parameters




### -param pBuffer






#### - pbBuffer [in]

Pointer to the buffer being passed to the allocator


## -returns



<code>PutBuffer</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The miniport driver does not need to use this method because when the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a>, the allocator looks at the <b>cbEvent</b> member of the <a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a> structure to determine if <b>uData</b> is a pointer or just data. If <b>cbEvent</b> specifies that the event data is greater than the storage capacity of <b>uData</b> (4 bytes on a 32-bit system and 8 bytes on a 64-bit system), the allocator simply assumes that <b>uData</b> points to a buffer that can be reused.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536791">IMXF::PutMessage</a>



<a href="..\dmusicks\nn-dmusicks-iallocatormxf.md">IAllocatorMXF</a>



<a href="..\dmusicks\ns-dmusicks-_dmus_kernel_event.md">DMUS_KERNEL_EVENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAllocatorMXF::PutBuffer method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

