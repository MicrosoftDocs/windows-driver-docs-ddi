---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VF_PARAMETERS
title: _NDIS_NIC_SWITCH_VF_PARAMETERS
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VF_PARAMETERS specifies the resource parameters of a PCI Express (PCIe) Virtual Function (VF) on a network adapter.
old-location: netvista\ndis_nic_switch_vf_parameters.htm
old-project: netvista
ms.assetid: 9e75bb9a-e266-4321-8862-4bdfab300421
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NDIS_NIC_SWITCH_VF_PARAMETERS, PNDIS_NIC_SWITCH_VF_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_NIC_SWITCH_VF_PARAMETERS, NDIS_NIC_SWITCH_VF_PARAMETERS, PNDIS_NIC_SWITCH_VF_PARAMETERS, netvista.ndis_nic_switch_vf_parameters, NDIS_NIC_SWITCH_VF_PARAMETERS structure [Network Drivers Starting with Windows Vista], *PNDIS_NIC_SWITCH_VF_PARAMETERS, _NDIS_NIC_SWITCH_VF_PARAMETERS
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
-	NDIS_NIC_SWITCH_VF_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VF_PARAMETERS, *PNDIS_NIC_SWITCH_VF_PARAMETERS
---

# _NDIS_NIC_SWITCH_VF_PARAMETERS structure


## -description


The <b>NDIS_NIC_SWITCH_VF_PARAMETERS</b> specifies the resource parameters of a PCI Express (PCIe) Virtual Function (VF) on a network adapter.


## -syntax


````
typedef struct _NDIS_NIC_SWITCH_VF_PARAMETERS {
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
} NDIS_NIC_SWITCH_VF_PARAMETERS, *PNDIS_NIC_SWITCH_VF_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VF_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VF_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.


### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. This value identifies the network adapter switch on which the VF is allocated.

The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.


<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div><div> </div>

### -field VMName

An NDIS_VM_NAME value that specifies the internal name of the Hyper-V child partition that is attached to the VF.


<div class="alert"><b>Note</b>  The Hyper-V child partition is also known as a virtual machine (VM).</div><div> </div>

### -field VMFriendlyName

An NDIS_VM_FRIENDLYNAME value that specifies the external name of the Hyper-V child partition that is attached to the VF. This member contains the user-friendly description of the partition.




### -field NicName

An NDIS_SWITCH_NIC_NAME value that specifies the name of the virtual machine (VM)  network adapter. This member contains the user-friendly description of the network adapter.



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


##### - Header.NDIS_NIC_SWITCH_VF_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VF_PARAMETERS_REVISION_1.


## -remarks


The  <b>NDIS_NIC_SWITCH_VF_PARAMETERS</b> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451824">OID_NIC_SWITCH_VF_PARAMETERS</a>.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451824">OID_NIC_SWITCH_VF_PARAMETERS</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_VF_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

