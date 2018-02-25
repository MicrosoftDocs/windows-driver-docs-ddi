---
UID: NS:ntddndis._NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
title: "_NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO"
author: windows-driver-content
description: The NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure specifies the PCI Express (PCIe) vendor and device identifiers (IDs) for a PCIe Virtual Function (VF) network adapter.
old-location: netvista\ndis_sriov_vf_vendor_device_id_info.htm
old-project: netvista
ms.assetid: ecf9f34a-ba05-4ad1-990c-b13d53fd78bb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, ,, C, D, E, F, I, N, NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure [Network Drivers Starting with Windows Vista], O, P, PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure pointer [Network Drivers Starting with Windows Vista], R, S, V, _, _NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, netvista.ndis_sriov_vf_vendor_device_id_info, ntddndis/NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, ntddndis/PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, *PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
---

# _NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure


## -description



The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure specifies the PCI Express (PCIe) vendor and device identifiers (IDs) for a PCIe Virtual Function (VF) network adapter. This virtual adapter is exposed within the guest operating system that runs in a Hyper-V child partition. 

The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure contains information that is used for PnP device enumeration in the guest operating system.




## -syntax


````
typedef struct _NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO {
  NDIS_OBJECT_HEADER     Header;
  NDIS_SRIOV_FUNCTION_ID VFId;
  USHORT                 VendorId;
  USHORT                 DeviceId;
} NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, *PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_VENDOR_DEVICE_ID_INFO_REVISION_1.


### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF network adapter.

<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

### -field VendorId

A USHORT value that uniquely identifies the vendor of the VF network adapter.


### -field DeviceId

A USHORT value that uniquely identifies the device type of the VF network adapter.


## -remarks



 The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure is used in the OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451913">OID_SRIOV_VF_VENDOR_DEVICE_ID</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451913">OID_SRIOV_VF_VENDOR_DEVICE_ID</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

