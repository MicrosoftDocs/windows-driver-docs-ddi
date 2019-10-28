---
UID: NS:ndis._NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
title: _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS (ndis.h)
description: The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider characteristics.
old-location: netvista\ndis_shared_memory_provider_characteristics.htm
tech.root: netvista
ms.assetid: 45001da1-5fe3-4383-8da7-31e3ee115c1f
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis/NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis/PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis_shared_memory_ref_0cb54ab1-d469-4fa0-833a-eb17e1441e76.xml, netvista.ndis_shared_memory_provider_characteristics"
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
product:
- Windows
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-allocate_shared_memory_handler">
     NetAllocateSharedMemory</a> function.


### -field FreeSharedMemoryHandler

An entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-free_shared_memory_handler">NetFreeSharedMemory</a> function.


## -remarks



To specify entry points for shared memory services, an NDIS driver initializes an
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure and passes it to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">
    NdisSetOptionalHandlers</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-allocate_shared_memory_handler">NetAllocateSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-free_shared_memory_handler">NetFreeSharedMemory</a>
 

 

