---
UID: NS:ndis._NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
title: "_NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider characteristics.
old-location: netvista\ndis_shared_memory_provider_characteristics.htm
old-project: netvista
ms.assetid: 45001da1-5fe3-4383-8da7-31e3ee115c1f
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis/NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis/PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis_shared_memory_ref_0cb54ab1-d469-4fa0-833a-eb17e1441e76.xml, netvista.ndis_shared_memory_provider_characteristics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, *PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
---

# _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure


## -description


The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider
  characteristics.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_SHARED_MEMORY_PROVIDER_CHARACTERISTICS_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field ProviderContext

An NDIS_HANDLE to a block of driver-allocated context information that stores information about
     the provider. NDIS passes the context information in calls to 
     <i>NetXxxSharedMemory</i> functions at the 
     <i>ProviderContext</i> parameter.


### -field AllocateSharedMemoryHandler

An entry point for the 
     <a href="https://msdn.microsoft.com/d85b4f28-707b-4525-afd8-83e1ceb2674e">
     NetAllocateSharedMemory</a> function.


### -field FreeSharedMemoryHandler

An entry point for the 
     <a href="https://msdn.microsoft.com/fdc3dfe7-6980-493d-ad41-aed501db3a6b">NetFreeSharedMemory</a> function.


## -remarks



To specify entry points for shared memory services, an NDIS driver initializes an
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure and passes it to the 
    <a href="https://msdn.microsoft.com/97649f4f-942a-47fc-a541-6f160c8b4eb4">
    NdisSetOptionalHandlers</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/d85b4f28-707b-4525-afd8-83e1ceb2674e">NetAllocateSharedMemory</a>



<a href="https://msdn.microsoft.com/fdc3dfe7-6980-493d-ad41-aed501db3a6b">NetFreeSharedMemory</a>
 

 

