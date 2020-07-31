---
UID: NS:ntddndis._NDIS_SRIOV_PROBED_BARS_INFO
title: _NDIS_SRIOV_PROBED_BARS_INFO (ntddndis.h)
description: The NDIS_SRIOV_PROBED_BARS_INFO structure specifies the values of the PCI Express (PCIe) Base Address Registers (BARs) of a network adapter that supports the single root I/O virtualization (SR-IOV) interface.
old-location: netvista\ndis_sriov_probed_bars_info.htm
tech.root: netvista
ms.assetid: 9f37d9e7-ae8b-448e-a535-f34b01c2bf8a
ms.date: 05/02/2018
keywords: ["_NDIS_SRIOV_PROBED_BARS_INFO structure"]
ms.keywords: "*PNDIS_SRIOV_PROBED_BARS_INFO, NDIS_SRIOV_PROBED_BARS_INFO, NDIS_SRIOV_PROBED_BARS_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_PROBED_BARS_INFO, PNDIS_SRIOV_PROBED_BARS_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_PROBED_BARS_INFO, netvista.ndis_sriov_probed_bars_info, ntddndis/NDIS_SRIOV_PROBED_BARS_INFO, ntddndis/PNDIS_SRIOV_PROBED_BARS_INFO"
f1_keywords:
 - "ntddndis/NDIS_SRIOV_PROBED_BARS_INFO"
 - "NDIS_SRIOV_PROBED_BARS_INFO"
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
- NDIS_SRIOV_PROBED_BARS_INFO
targetos: Windows
req.typenames: NDIS_SRIOV_PROBED_BARS_INFO, *PNDIS_SRIOV_PROBED_BARS_INFO
---

# _NDIS_SRIOV_PROBED_BARS_INFO structure


## -description



The <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure specifies the values of the PCI Express (PCIe) Base Address Registers (BARs) of a network adapter that supports the single root I/O virtualization (SR-IOV) interface. 
 

The values specified by the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure are those that were reported by the adapter following a query that was performed by the PCI bus driver. This query determines the memory or I/O address space that is required by the device.






## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_PROBED_BARS_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_PROBED_BARS_INFO_REVISION_1.


### -field BaseRegisterValuesOffset

A ULONG value that contains the offset, in units of bytes, from the beginning of this structure to an array of ULONG values. The array  contains a ULONG value for each BAR of the PCIe network adapter.

The maximum number of elements within this array is PCI_TYPE0_ADDRESSES.

For more information, see the Remarks section.


## -remarks



The <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure is used in OID query requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-probed-bars">OID_SRIOV_PROBED_BARS</a>.  Each
    element in the array that follows the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure contains a ULONG value for a BAR of the network adapter. The offsets of the elements within the array must match the offsets of the BARs on the adapter.

<div class="alert"><b>Note</b>  Each element in the array must contain the BAR value that was returned during the BAR query that was performed by the PCI bus driver.</div>
<div> </div>
For more information about the base address registers of a PCI device, see the <i>PCI Local Bus Specification</i>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-probed-bars">OID_SRIOV_PROBED_BARS</a>
 

 

