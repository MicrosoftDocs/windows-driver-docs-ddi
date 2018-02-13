---
UID: NC:ks.PFNALLOCATOR_FREEFRAME
title: PFNALLOCATOR_FREEFRAME
author: windows-driver-content
description: The KStrFreeFrame routine describes a vendor-supplied frame deallocation function.
old-location: stream\kstrfreeframe.htm
old-project: stream
ms.assetid: 6e998b5a-7f2a-4ab2-9382-f70476e5f34f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kstrfreeframe, KStrFreeFrame routine [Streaming Media Devices], KStrFreeFrame, PFNALLOCATOR_FREEFRAME, PFNALLOCATOR_FREEFRAME, ks/KStrFreeFrame, ksfunc_fbbb5f23-02d9-4670-8e9a-c157402d413e.xml
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
-	KStrFreeFrame
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNALLOCATOR_FREEFRAME callback


## -description


The <i>KStrFreeFrame</i> routine describes a vendor-supplied frame deallocation function. 


## -prototype


````
PFNALLOCATOR_FREEFRAME KStrFreeFrame;

VOID KStrFreeFrame(
  _In_ PFILE_OBJECT FileObject,
  _In_ PVOID        Frame
)
{ ... }
````


## -parameters




### -param FileObject [in]

Pointer to a <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure for which this frame has been allocated.


### -param Frame [in]

A pointer to a buffer containing the frame to release.


## -returns



Returns STATUS_SUCCESS if the request is handled.  Otherwise returns an appropriate error code.




## -remarks



This type is used in the <b>FreeFrame</b> member of the <a href="..\ks\ns-ks-ksstreamallocator_functiontable.md">KSSTREAMALLOCATOR_FUNCTIONTABLE</a> structure.

You can pass an instance of this structure as part of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a> property request.




## -see-also

<a href="..\ks\ns-ks-ksstreamallocator_functiontable.md">KSSTREAMALLOCATOR_FUNCTIONTABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrFreeFrame routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

