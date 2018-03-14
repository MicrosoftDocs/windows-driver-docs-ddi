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



 

 


