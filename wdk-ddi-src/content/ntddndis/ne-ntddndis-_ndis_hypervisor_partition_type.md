---
UID: NE:ntddndis._NDIS_HYPERVISOR_PARTITION_TYPE
title: _NDIS_HYPERVISOR_PARTITION_TYPE (ntddndis.h)
description: The NDIS_HYPERVISOR_PARTITION_TYPE enumeration identifies the current partition type that is running on the hypervisor.
old-location: netvista\ndis_hypervisor_partition_type.htm
tech.root: netvista
ms.assetid: 830460f8-4cd6-4a52-ac32-004dc4a204e3
ms.date: 05/02/2018
ms.keywords: "*PNDIS_HYPERVISOR_PARTITION_TYPE, NDIS_HYPERVISOR_PARTITION_TYPE, NDIS_HYPERVISOR_PARTITION_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisHypervisorPartitionMsHvChild, NdisHypervisorPartitionTypeMax, NdisHypervisorPartitionTypeMsHvParent, NdisHypervisorPartitionTypeUnknown, PNDIS_HYPERVISOR_PARTITION_TYPE, PNDIS_HYPERVISOR_PARTITION_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_HYPERVISOR_PARTITION_TYPE, netvista.ndis_hypervisor_partition_type, ntddndis/NDIS_HYPERVISOR_PARTITION_TYPE, ntddndis/NdisHypervisorPartitionMsHvChild, ntddndis/NdisHypervisorPartitionTypeMax, ntddndis/NdisHypervisorPartitionTypeMsHvParent, ntddndis/NdisHypervisorPartitionTypeUnknown, ntddndis/PNDIS_HYPERVISOR_PARTITION_TYPE, virtual_machine_queue_ref_582bebe7-e184-4460-8437-b81bcd6dbf8b.xml"
ms.topic: enum
req.header: ntddndis.h
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
-	Ntddndis.h
api_name:
-	NDIS_HYPERVISOR_PARTITION_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_HYPERVISOR_PARTITION_TYPE, *PNDIS_HYPERVISOR_PARTITION_TYPE
---

# _NDIS_HYPERVISOR_PARTITION_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  <p class="note">Starting with Windows 10 Version 1703, NDIS_HYPERVISOR_PARTITION_TYPE is deprecated and should not be used.  Drivers are encouraged to move away from it, as it may not be available in future versions of the operating system. 

<p class="note">Drivers should instead follow a hypervisor's instructions to query hypervisor presence and capabilities. For example, Hyper-V's instructions are documented in the <a href="https://docs.microsoft.com/virtualization/hyper-v-on-windows/reference/tlfs">Top-Level Functional Specification</a>.

</div><div> </div>The <b>NDIS_HYPERVISOR_PARTITION_TYPE</b> enumeration identifies the current partition type that is running
  on the hypervisor.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565708">NDIS_HYPERVISOR_INFO</a>
 

 

