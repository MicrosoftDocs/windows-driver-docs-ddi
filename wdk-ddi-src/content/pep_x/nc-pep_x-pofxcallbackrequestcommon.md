---
UID: NC:pep_x.POFXCALLBACKREQUESTCOMMON
title: POFXCALLBACKREQUESTCOMMON (pep_x.h)
description: The RequestCommon routine is a generic request handler.
old-location: kernel\requestcommon.htm
tech.root: kernel
ms.assetid: 16699B3D-D02B-4D01-9EBE-003C92B06D31
ms.date: 04/30/2018
ms.keywords: POFXCALLBACKREQUESTCOMMON, RequestCommon, RequestCommon routine [Kernel-Mode Driver Architecture], kernel.requestcommon, pepfx/RequestCommon
ms.topic: callback
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: "<= HIGH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- pepfx.h
api_name:
- RequestCommon
product:
- Windows
targetos: Windows
req.typenames: 
---

# POFXCALLBACKREQUESTCOMMON callback function


## -description


The <b>RequestCommon</b> routine is a generic request handler.


## -parameters




### -param RequestId [in]

A request ID that specifies the operation being requested. 


### -param Data [in, out, optional]

A pointer to a data structure that contains the input data and/or result data for the request specified by the <i>RequestId</i> parameter. 


## -returns



<b>RequestCommon</b> returns STATUS_SUCCESS if the request is successfully handled. Otherwise, it returns an appropriate error status code.




## -remarks



This routine is implemented by the <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) and is called by the platform extension plug-in (PEP). The <b>RequestCommon</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>RequestCommon</b> routine.

A PEP can call this routine at IRQL <= HIGH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
 

 

