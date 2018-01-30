---
UID: NC:pepfx.POFXCALLBACKREQUESTCOMMON
title: POFXCALLBACKREQUESTCOMMON
author: windows-driver-content
description: The RequestCommon routine is a generic request handler.
old-location: kernel\requestcommon.htm
old-project: kernel
ms.assetid: 16699B3D-D02B-4D01-9EBE-003C92B06D31
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.requestcommon, RequestCommon, RequestCommon routine [Kernel-Mode Driver Architecture], RequestCommon, POFXCALLBACKREQUESTCOMMON, POFXCALLBACKREQUESTCOMMON, pepfx/RequestCommon
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pepfx.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	pepfx.h
apiname:
-	RequestCommon
product: Windows
targetos: Windows
req.typenames: "*PVPCI_PNP_ID, VPCI_PNP_ID"
---

# POFXCALLBACKREQUESTCOMMON callback


## -description


The <b>RequestCommon</b> routine is a generic request handler.


## -prototype


````
POFXCALLBACKREQUESTCOMMON RequestCommon;

NTSTATUS RequestCommon(
  _In_        ULONG RequestId,
  _Inout_opt_ PVOID Data
)
{ ... }
````


## -parameters




### -param RequestId [in]

A request ID that specifies the operation being requested. 


### -param Data [in, out, optional]

A pointer to a data structure that contains the input data and/or result data for the request specified by the <i>RequestId</i> parameter. 


## -returns


<b>RequestCommon</b> returns STATUS_SUCCESS if the request is successfully handled. Otherwise, it returns an appropriate error status code.



## -remarks


This routine is implemented by the <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) and is called by the platform extension plug-in (PEP). The <b>RequestCommon</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>RequestCommon</b> routine.

A PEP can call this routine at IRQL &lt;= HIGH_LEVEL.



## -see-also

<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKREQUESTCOMMON routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

