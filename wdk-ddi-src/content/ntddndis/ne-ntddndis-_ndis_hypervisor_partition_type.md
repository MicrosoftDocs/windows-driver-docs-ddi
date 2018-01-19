---
UID: NE:ntddndis._NDIS_HYPERVISOR_PARTITION_TYPE
title: _NDIS_HYPERVISOR_PARTITION_TYPE
author: windows-driver-content
description: The NDIS_HYPERVISOR_PARTITION_TYPE enumeration identifies the current partition type that is running on the hypervisor.
old-location: netvista\ndis_hypervisor_partition_type.htm
old-project: netvista
ms.assetid: 830460f8-4cd6-4a52-ac32-004dc4a204e3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_HYPERVISOR_PARTITION_TYPE, NDIS_HYPERVISOR_PARTITION_TYPE, *PNDIS_HYPERVISOR_PARTITION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_HYPERVISOR_PARTITION_TYPE
req.alt-loc: Ntddndis.h
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
req.typenames: NDIS_HYPERVISOR_PARTITION_TYPE, *PNDIS_HYPERVISOR_PARTITION_TYPE
---

# _NDIS_HYPERVISOR_PARTITION_TYPE enumeration



## -description

## -syntax

````
typedef enum _NDIS_HYPERVISOR_PARTITION_TYPE { 
  NdisHypervisorPartitionTypeUnknown,
  NdisHypervisorPartitionTypeMsHvParent,
  NdisHypervisorPartitionMsHvChild,
  NdisHypervisorPartitionTypeMax
} NDIS_HYPERVISOR_PARTITION_TYPE, *PNDIS_HYPERVISOR_PARTITION_TYPE;
````


## -enum-fields

### -field NdisHypervisorPartitionTypeUnknown

The partition type that is running on the hypervisor is not known.

<div class="alert"><b>Note</b>  This enumeration value is used to identify a partition type for a third-party hypervisor.</div>
<div> </div>

### -field NdisHypervisorPartitionTypeMsHvParent

The parent partition (also known as the root partition) is running
     on the Microsoft hypervisor.


### -field NdisHypervisorPartitionMsHvChild

The child partition is running on
     the Microsoft hypervisor.


### -field NdisHypervisorPartitionTypeMax

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks
For more information about Hyper-V parent and child partitions, see <a href="https://msdn.microsoft.com/467996B2-9319-47F9-BAEB-5AC1F20B6E01">Virtualized Networking Concepts and Terms</a>.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_hypervisor_info.md">NDIS_HYPERVISOR_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_HYPERVISOR_PARTITION_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

