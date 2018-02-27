---
UID: NS:ndis._NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
title: "_NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider characteristics.
old-location: netvista\ndis_shared_memory_provider_characteristics.htm
old-project: netvista
ms.assetid: 45001da1-5fe3-4383-8da7-31e3ee115c1f
ms.author: windowsdriverdev
ms.date: 2/16/2018
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, *PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
---

# _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure


## -description


The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider
  characteristics.


## -syntax


````
typedef struct _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER             Header;
  ULONG                          Flags;
  NDIS_HANDLE                    ProviderContext;
  ALLOCATE_SHARED_MEMORY_HANDLER AllocateSharedMemoryHandler;
  FREE_SHARED_MEMORY_HANDLER     FreeSharedMemoryHandler;
} NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, *PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
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
     <a href="..\ndis\nc-ndis-allocate_shared_memory_handler.md">
     NetAllocateSharedMemory</a> function.


### -field FreeSharedMemoryHandler

An entry point for the 
     <a href="..\ndis\nc-ndis-free_shared_memory_handler.md">NetFreeSharedMemory</a> function.


## -remarks



To specify entry points for shared memory services, an NDIS driver initializes an
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure and passes it to the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
    NdisSetOptionalHandlers</a> function.




## -see-also

<a href="..\ndis\nc-ndis-free_shared_memory_handler.md">NetFreeSharedMemory</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\nc-ndis-allocate_shared_memory_handler.md">NetAllocateSharedMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

