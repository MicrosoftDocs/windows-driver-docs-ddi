---
UID: NC:ks.PFNALLOCATOR_ALLOCATEFRAME
title: PFNALLOCATOR_ALLOCATEFRAME
author: windows-driver-content
description: The KStrAllocateFrame routine describes a vendor-supplied frame allocation function.
old-location: stream\kstrallocateframe.htm
old-project: stream
ms.assetid: 1b6eec23-82b4-4e8f-89d0-e76d6449906e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: KStrAllocateFrame, KStrAllocateFrame routine [Streaming Media Devices], PFNALLOCATOR_ALLOCATEFRAME, ks/KStrAllocateFrame, ksfunc_a90af96e-53df-43f5-b847-ba1876b788fd.xml, stream.kstrallocateframe
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	KStrAllocateFrame
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNALLOCATOR_ALLOCATEFRAME callback


## -description


The <i>KStrAllocateFrame</i> routine describes a vendor-supplied frame allocation function. 


## -prototype


````
PFNALLOCATOR_ALLOCATEFRAME KStrAllocateFrame;

NTSTATUS KStrAllocateFrame(
  _In_  PFILE_OBJECT FileObject,
  _Out_ PVOID        *Frame
)
{ ... }
````


## -parameters




### -param FileObject [in]

Pointer to a <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure for which to allocate frames.


### -param *Frame [out]

A pointer to a caller-allocated buffer in which the new frame is returned.


## -returns



Returns STATUS_SUCCESS if the request is handled.  Otherwise returns an appropriate error code.




## -remarks



This type is used in the <b>AllocateFrame</b> member of the <a href="..\ks\ns-ks-ksstreamallocator_functiontable.md">KSSTREAMALLOCATOR_FUNCTIONTABLE</a> structure.

You can pass an instance of this structure as part of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a> property request.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a>



<a href="..\ks\ns-ks-ksstreamallocator_functiontable.md">KSSTREAMALLOCATOR_FUNCTIONTABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrAllocateFrame routine%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

