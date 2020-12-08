---
UID: NS:ntddndis._NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
title: _NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO (ntddndis.h)
description: The NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure specifies the PCI Express (PCIe) vendor and device identifiers (IDs) for a PCIe Virtual Function (VF) network adapter.
old-location: netvista\ndis_sriov_vf_vendor_device_id_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure"]
ms.keywords: "*PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, netvista.ndis_sriov_vf_vendor_device_id_info, ntddndis/NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, ntddndis/PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO"
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
targetos: Windows
req.typenames: NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, *PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
f1_keywords:
 - _NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
 - ntddndis/_NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
 - PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
 - ntddndis/PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
 - NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
 - ntddndis/NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
---

# _NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure


## -description

The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure specifies the PCI Express (PCIe) vendor and device identifiers (IDs) for a PCIe Virtual Function (VF) network adapter. This virtual adapter is exposed within the guest operating system that runs in a Hyper-V child partition. 

The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure contains information that is used for PnP device enumeration in the guest operating system.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_VF_VENDOR_DEVICE_ID_INFO_REVISION_1.

### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF network adapter.

<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID set request of <a href="/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

### -field VendorId

A USHORT value that uniquely identifies the vendor of the VF network adapter.

### -field DeviceId

A USHORT value that uniquely identifies the device type of the VF network adapter.

## -remarks

 The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure is used in the OID method requests of <a href="/windows-hardware/drivers/network/oid-sriov-vf-vendor-device-id">OID_SRIOV_VF_VENDOR_DEVICE_ID</a>.

## -see-also

<b></b>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>



<a href="/windows-hardware/drivers/network/oid-sriov-vf-vendor-device-id">OID_SRIOV_VF_VENDOR_DEVICE_ID</a>
