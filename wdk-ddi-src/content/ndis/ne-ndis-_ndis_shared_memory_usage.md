---
UID: NE:ndis._NDIS_SHARED_MEMORY_USAGE
title: "_NDIS_SHARED_MEMORY_USAGE"
author: windows-driver-content
description: The NDIS_SHARED_MEMORY_USAGE enumeration specifies how shared memory is used.
old-location: netvista\ndis_shared_memory_usage.htm
old-project: netvista
ms.assetid: c46102dd-26ea-459b-8cc2-f7e2d2e2f2ad
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE enumeration [Network Drivers Starting with Windows Vista], NdisSharedMemoryUsageMax, NdisSharedMemoryUsageOther, NdisSharedMemoryUsageReceive, NdisSharedMemoryUsageReceiveData, NdisSharedMemoryUsageReceiveHeader, NdisSharedMemoryUsageReceiveLookahead, NdisSharedMemoryUsageReceivePostLookahead, NdisSharedMemoryUsageUndefined, NdisSharedMemoryUsageXmit, NdisSharedMemoryUsageXmitData, NdisSharedMemoryUsageXmitHeader, PNDIS_SHARED_MEMORY_USAGE, PNDIS_SHARED_MEMORY_USAGE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_SHARED_MEMORY_USAGE, ndis/NDIS_SHARED_MEMORY_USAGE, ndis/NdisSharedMemoryUsageMax, ndis/NdisSharedMemoryUsageOther, ndis/NdisSharedMemoryUsageReceive, ndis/NdisSharedMemoryUsageReceiveData, ndis/NdisSharedMemoryUsageReceiveHeader, ndis/NdisSharedMemoryUsageReceiveLookahead, ndis/NdisSharedMemoryUsageReceivePostLookahead, ndis/NdisSharedMemoryUsageUndefined, ndis/NdisSharedMemoryUsageXmit, ndis/NdisSharedMemoryUsageXmitData, ndis/NdisSharedMemoryUsageXmitHeader, ndis/PNDIS_SHARED_MEMORY_USAGE, ndis_shared_memory_ref_fc268c92-4745-4916-8aab-e1e67e12d217.xml, netvista.ndis_shared_memory_usage"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_SHARED_MEMORY_USAGE
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# _NDIS_SHARED_MEMORY_USAGE enumeration


## -description


The NDIS_SHARED_MEMORY_USAGE enumeration specifies how shared memory is used.


## -enum-fields




### -field NdisSharedMemoryUsageUndefined

The shared memory application is not defined.


### -field NdisSharedMemoryUsageXmit

The shared memory contains transmit data buffers.


### -field NdisSharedMemoryUsageXmitHeader

The shared memory contains transmit header buffers.


### -field NdisSharedMemoryUsageXmitData

The shared memory contains transmit data.


### -field NdisSharedMemoryUsageReceive

The shared memory contains receive data buffers.


### -field NdisSharedMemoryUsageReceiveLookahead

The shared memory contains receive lookahead buffers.


### -field NdisSharedMemoryUsageReceivePostLookahead

The shared memory contains received post lookahead information.


### -field NdisSharedMemoryUsageReceiveHeader

The shared memory contains receive header information.


### -field NdisSharedMemoryUsageReceiveData

The shared memory contains receive data.


### -field NdisSharedMemoryUsageOther

The shared memory application is not specified.


### -field NdisSharedMemoryUsageMax

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The NDIS_SHARED_MEMORY_USAGE enumeration is used in the 
    <a href="https://msdn.microsoft.com/286b08f6-179e-426e-ae65-b108529d049a">
    NDIS_SHARED_MEMORY_PARAMETERS</a> and 
    <a href="https://msdn.microsoft.com/5c14a6ed-3180-41d6-a09a-b3ae0a0c8b36">
    NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structures.




## -see-also




<a href="https://msdn.microsoft.com/5c14a6ed-3180-41d6-a09a-b3ae0a0c8b36">
   NDIS_SCATTER_GATHER_LIST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567303">NDIS_SHARED_MEMORY_PARAMETERS</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SHARED_MEMORY_USAGE enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
