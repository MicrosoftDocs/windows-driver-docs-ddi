---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VF_INFO
title: "_NDIS_NIC_SWITCH_VF_INFO"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VF_INFO structure specifies the information about a PCI Express (PCIe) Virtual Function (VF) that has been allocated on the network adapter.
old-location: netvista\ndis_nic_switch_vf_info.htm
old-project: netvista
ms.assetid: 1af8b1cd-c594-49c7-8c25-674226295d90
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_NIC_SWITCH_VF_INFO, ,, C, D, F, H, I, N, NDIS_NIC_SWITCH_VF_INFO, NDIS_NIC_SWITCH_VF_INFO structure [Network Drivers Starting with Windows Vista], O, P, PNDIS_NIC_SWITCH_VF_INFO, PNDIS_NIC_SWITCH_VF_INFO structure pointer [Network Drivers Starting with Windows Vista], S, T, V, W, _, _NDIS_NIC_SWITCH_VF_INFO, netvista.ndis_nic_switch_vf_info, ntddndis/NDIS_NIC_SWITCH_VF_INFO, ntddndis/PNDIS_NIC_SWITCH_VF_INFO"
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
-	NDIS_NIC_SWITCH_VF_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VF_INFO, *PNDIS_NIC_SWITCH_VF_INFO
---

# _NDIS_NIC_SWITCH_VF_INFO structure


## -description


The <b>NDIS_NIC_SWITCH_VF_INFO</b> structure specifies the information about a PCI Express (PCIe) Virtual Function (VF) that has been allocated on the network adapter.


## -syntax


````
typedef struct _NDIS_NIC_SWITCH_VF_INFO {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  Flags;
  NDIS_NIC_SWITCH_ID     SwitchId;
  NDIS_VM_NAME           VMName;
  NDIS_VM_FRIENDLYNAME   VMFriendlyName;
  NDIS_SWITCH_NIC_NAME   NicName;
  USHORT                 MacAddressLength;
  UCHAR                  PermanentMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  UCHAR                  CurrentMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  NDIS_SRIOV_FUNCTION_ID VFId;
  NDIS_VF_RID            RequestorId;
} NDIS_NIC_SWITCH_VF_INFO, *PNDIS_NIC_SWITCH_VF_INFO;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VF_INFO</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VF_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_VF_INFO_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VF_INFO_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.


### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

### -field VMName

An NDIS_VM_NAME value that specifies the name of the Hyper-V child partition that is attached to the VF. This member contains the user-friendly description of the partition.

<div class="alert"><b>Note</b>  The Hyper-V child partition is also known as a virtual machine (VM).</div>
<div> </div>

### -field VMFriendlyName

An NDIS_VM_FRIENDLYNAME value that specifies the external name of the Hyper-V child partition that is attached to the VF. This member contains the user-friendly description of the partition.




### -field NicName

An NDIS_SWITCH_NIC_NAME value that specifies the name of the virtual machine (VM) network adapter. This member contains the user-friendly description of the network adapter.



The VM network adapter is a virtual device that is exposed in the guest operating system that runs in a Hyper-V child partition. The VM network adapter teams with the VF network adapter to provide the hardware-based VF data path over the SR-IOV interface. 

For more information about the VF data path, see <a href="https://msdn.microsoft.com/0DC2327E-3A58-46BC-A3D6-3AFD24ABC901">SR-IOV VF Data Path</a>.


### -field MacAddressLength

A USHORT value that specifies the length of the <b>PermanentMacAddress</b> and <b>CurrentMacAddress</b> members.


### -field PermanentMacAddress

The permanent MAC address of the VF. This is the permanent MAC address for the VF network adapter that is exposed in the guest operating system.


### -field CurrentMacAddress

The current MAC address of the VF. This is the current MAC address for the VF network adapter that is exposed in the guest operating system.


### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.


### -field RequestorId

An NDIS_VF_RID that specifies the PCI Express (PCIe) Requestor ID (RID) of the VF.


## -remarks



An <b>NDIS_NIC_SWITCH_VF_INFO</b> structure contains information about a VF that was previously created through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>. When this OID request is issued, one or more <b>NDIS_NIC_SWITCH_VF_INFO</b> structures are returned within an <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vf_info_array.md">NDIS_NIC_SWITCH_VF_INFO_ARRAY</a> structure.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vf_info_array.md">NDIS_NIC_SWITCH_VF_INFO_ARRAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_VF_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

