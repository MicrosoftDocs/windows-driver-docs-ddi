---
UID: NS:ntddndis._NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS
title: _NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS (ntddndis.h)
description: The NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure specifies the parameters for a read operation on the configuration block of a network adapter's PCI Express (PCIe) Virtual Function (VF).
old-location: netvista\ndis_sriov_read_vf_config_block_parameters.htm
tech.root: netvista
ms.assetid: fafad6f2-8092-4067-afad-208877309010
ms.date: 05/02/2018
keywords: ["_NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure"]
ms.keywords: "*PNDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, PNDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, netvista.ndis_sriov_read_vf_config_block_parameters, ntddndis/NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, ntddndis/PNDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS"
f1_keywords:
 - "ntddndis/NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, *PNDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS
---

# _NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure


## -description


The <b>NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS</b> structure specifies the parameters for a read operation on the configuration block of a network adapter's PCI Express (PCIe) Virtual Function (VF). These parameters are used for the backchannel communication between the miniport drivers for a VF and the PCIe Physical Function (PF).


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1.


### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID method request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

### -field BlockId

A ULONG value that specifies the identifier of the VF configuration block to be read. This identifier is proprietary to the independent hardware vendor (IHV) and is used only by the miniport drivers for the PF and VF on the network adapter.


For more information, see the Remarks section.


### -field Length

A ULONG value that specifies the length, in units of bytes, of the read operation.


### -field BufferOffset

A ULONG value that specifies the offset, in units of bytes, from the beginning of this structure to a buffer that contains the data that is read from the specified VF configuration block.


## -remarks



The <b>NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS</b> structure is used in OID method requests of  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-read-vf-config-block">OID_SRIOV_READ_VF_CONFIG_BLOCK</a>.

A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. Data from a VF configuration block can be exchanged between the following drivers:

<ul>
<li>
The VF miniport driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.



</li>
<li>
The PF miniport driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
<div class="alert"><b>Note</b>  The  usage of the VF configuration block and the format of its configuration data are defined by the  independent hardware vendor (IHV) of the device. The configuration data is used only by the PF and VF miniport drivers.</div>
<div> </div>
For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/sr-iov-pf-vf-backchannel-communication">SR-IOV PF/VF Backchannel Communication</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-read-vf-config-block">OID_SRIOV_READ_VF_CONFIG_BLOCK</a>
 

 

