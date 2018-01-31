---
UID: NS:pepfx._PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
title: "_PEP_PPM_CONTEXT_QUERY_PARKING_PAGE"
author: windows-driver-content
description: The PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure describes the parking page for a processor.
old-location: kernel\pep_ppm_context_query_parking_page.htm
old-project: kernel
ms.assetid: F714D6EE-90F9-4FC6-95EB-32225284DC1F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure pointer [Kernel-Mode Driver Architecture], PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, *PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE, PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE, pepfx/PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, kernel.pep_ppm_context_query_parking_page, PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure [Kernel-Mode Driver Architecture], pepfx/PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE, _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, *PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE
---

# _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure


## -description


The <b>PEP_PPM_CONTEXT_QUERY_PARKING_PAGE</b> structure describes the parking page for a processor.


## -syntax


````
typedef struct _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE {
  PHYSICAL_ADDRESS PhysicalPageAddress;
  PVOID            VirtualPageAddress;
} PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, *PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE;
````


## -struct-fields




#### - PhysicalPageAddress

The physical memory address of the parking page.


#### - VirtualPageAddress

The virtual memory address of the parking page.


## -remarks


The output buffer for a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186798">PEP_PPM_POWER_CONTROL_QUERY_PARKING_PAGE</a> power control request is a <b>PEP_PPM_CONTEXT_QUERY_PARKING_PAGE</b> structure.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186798">PEP_PPM_POWER_CONTROL_QUERY_PARKING_PAGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

