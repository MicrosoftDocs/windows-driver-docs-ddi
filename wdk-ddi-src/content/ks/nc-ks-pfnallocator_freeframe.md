---
UID: NC:ks.PFNALLOCATOR_FREEFRAME
title: PFNALLOCATOR_FREEFRAME
author: windows-driver-content
description: The KStrFreeFrame routine describes a vendor-supplied frame deallocation function.
old-location: stream\kstrfreeframe.htm
old-project: stream
ms.assetid: 6e998b5a-7f2a-4ab2-9382-f70476e5f34f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrFreeFrame, KStrFreeFrame routine [Streaming Media Devices], PFNALLOCATOR_FREEFRAME, ks/KStrFreeFrame, ksfunc_fbbb5f23-02d9-4670-8e9a-c157402d413e.xml, stream.kstrfreeframe
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	KStrFreeFrame
product:
- Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNALLOCATOR_FREEFRAME callback


## -description


The <i>KStrFreeFrame</i> routine describes a vendor-supplied frame deallocation function. 


## -parameters




### -param FileObject [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure for which this frame has been allocated.


### -param Frame [in]

A pointer to a buffer containing the frame to release.


## -returns



Returns STATUS_SUCCESS if the request is handled.  Otherwise returns an appropriate error code.




## -remarks



This type is used in the <b>FreeFrame</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566862">KSSTREAMALLOCATOR_FUNCTIONTABLE</a> structure.

You can pass an instance of this structure as part of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a> property request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566862">KSSTREAMALLOCATOR_FUNCTIONTABLE</a>
 

 

