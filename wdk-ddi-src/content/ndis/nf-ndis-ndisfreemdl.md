---
UID: NF:ndis.NdisFreeMdl
title: NdisFreeMdl function
author: windows-driver-content
description: The NdisFreeMdl function frees an MDL that was allocated by calling the NdisAllocateMdl function.
old-location: netvista\ndisfreemdl.htm
old-project: netvista
ms.assetid: 612a66fa-0e0c-4eee-99b0-9bc09437b026
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFreeMdl, NdisFreeMdl function [Network Drivers Starting with Windows Vista], ndis/NdisFreeMdl, ndis_netbuf_functions_ref_0631fdd9-0961-43a9-a7a8-7d41e9d17220.xml, netvista.ndisfreemdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateMdl
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeMdl
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeMdl function


## -description


The 
  <b>NdisFreeMdl</b> function frees an MDL that was allocated by calling the 
  <a href="..\ndis\nf-ndis-ndisallocatemdl.md">NdisAllocateMdl</a> function.


## -syntax


````
VOID NdisFreeMdl(
  _In_ PMDL Mdl
);
````


## -parameters




### -param Mdl [in]

A pointer to the MDL that NDIS should free.


## -returns



None




## -see-also

<a href="..\ndis\nf-ndis-ndisallocatemdl.md">NdisAllocateMdl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeMdl function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

