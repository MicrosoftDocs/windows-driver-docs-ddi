---
UID: NS:ntddndis._NDIS_HYPERVISOR_INFO
title: _NDIS_HYPERVISOR_INFO (ntddndis.h)
description: The NDIS_HYPERVISOR_INFO structure contains information about the hypervisor that is present on the system.
old-location: netvista\ndis_hypervisor_info.htm
tech.root: netvista
ms.assetid: 847987d4-f67b-4e88-9a8d-9be4ad9be80d
ms.date: 05/02/2018
keywords: ["_NDIS_HYPERVISOR_INFO structure"]
ms.keywords: "*PNDIS_HYPERVISOR_INFO, NDIS_HYPERVISOR_INFO, NDIS_HYPERVISOR_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_HYPERVISOR_INFO, PNDIS_HYPERVISOR_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_HYPERVISOR_INFO, netvista.ndis_hypervisor_info, ntddndis/NDIS_HYPERVISOR_INFO, ntddndis/PNDIS_HYPERVISOR_INFO, virtual_machine_queue_ref_c0f9611a-2d20-4757-ba59-16bf6a83549c.xml"
f1_keywords:
 - "ntddndis/NDIS_HYPERVISOR_INFO"
 - "NDIS_HYPERVISOR_INFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddndis.h
api_name:
- NDIS_HYPERVISOR_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_HYPERVISOR_INFO, *PNDIS_HYPERVISOR_INFO
---

# _NDIS_HYPERVISOR_INFO structure


## -description


<div class="alert"><b>Important</b>  <p class="note">Starting with Windows 10 Version 1703, NDIS_HYPERVISOR_INFO is deprecated and should not be used.  Drivers are encouraged to move away from it, as it may not be available in future versions of the operating system. 

<p class="note">Drivers should instead follow a hypervisor's instructions to query hypervisor presence and capabilities. For example, Hyper-V's instructions are documented in the <a href="https://docs.microsoft.com/virtualization/hyper-v-on-windows/reference/tlfs">Top-Level Functional Specification</a>.

</div><div> </div>The <b>NDIS_HYPERVISOR_INFO</b> structure contains information about the hypervisor that is present on the
  system.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_HYPERVISOR_INFO</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_HYPERVISOR_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_HYPERVISOR_INFO_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to NDIS_SIZEOF_HYPERVISOR_INFO_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of the following flag.
     





#### NDIS_HYPERVISOR_INFO_FLAG_HYPERVISOR_PRESENT

Specifies that a hypervisor is present on the system.


### -field PartitionType

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_hypervisor_partition_type">
     NDIS_HYPERVISOR_PARTITION_TYPE</a> enumeration value that specifies the partition type that is running
     on the hypervisor.


## -remarks



The <b>NDIS_HYPERVISOR_INFO</b> structure specifies the hypervisor information that is returned by the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgethypervisorinfo">NdisGetHypervisorInfo</a> function.

NDIS drivers pass this structure to the 
    <b>NdisGetHypervisorInfo</b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_hypervisor_partition_type">NDIS_HYPERVISOR_PARTITION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgethypervisorinfo">NdisGetHypervisorInfo Function</a>
 

 

