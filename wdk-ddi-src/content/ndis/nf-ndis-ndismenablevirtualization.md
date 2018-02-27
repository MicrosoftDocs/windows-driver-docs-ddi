---
UID: NF:ndis.NdisMEnableVirtualization
title: NdisMEnableVirtualization function
author: windows-driver-content
description: A miniport driver calls the NdisMEnableVirtualization function during the creation or deletion of a NIC switch on the network adapter.
old-location: netvista\ndismenablevirtualization.htm
old-project: netvista
ms.assetid: 5a82dfe6-8844-4b18-8f54-7bf143fcd2ff
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisMEnableVirtualization, NdisMEnableVirtualization function [Network Drivers Starting with Windows Vista], ndis/NdisMEnableVirtualization, netvista.ndismenablevirtualization
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMEnableVirtualization
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMEnableVirtualization function


## -description


A miniport driver calls the <b>NdisMEnableVirtualization</b> function during the creation or deletion of a NIC switch on the network adapter. By calling this function, the driver configures the single root I/O virtualization (SR-IOV) Extended Capability structure in the PCI Express (PCIe) configuration space for the network adapter's Physical Function (PF).
<div class="alert"><b>Note</b>  <b>NdisMEnableVirtualization</b> must only be called by the miniport driver for the network adapter's PF.</div><div> </div>

## -syntax


````
NDIS_STATUS NdisMEnableVirtualization(
  _In_ NDIS_HANDLE NdisMiniportHandle,
  _In_ USHORT      NumVFs,
  _In_ BOOLEAN     EnableVFMigration,
  _In_ BOOLEAN     EnableMigrationInterrupt,
  _In_ BOOLEAN     EnableVirtualization
);
````


## -parameters




### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


### -param NumVFs [in]

A USHORT value that contains the number of  Virtual Functions (VFs) that are to be enabled for the network adapter.  <b>NdisMEnableVirtualization</b> sets the <b>NumVFs</b> member of the SR-IOV Extended Capability structure to the value of the <i>NumVFs</i> parameter. 

<div class="alert"><b>Note</b>  If the <i>EnableVirtualization</i> parameter is FALSE, <i>NumVFs</i> must be set to zero.</div>
<div> </div>

### -param EnableVFMigration [in]

 This parameter is reserved for NDIS and must be set to FALSE.


### -param EnableMigrationInterrupt [in]

 This parameter is reserved for NDIS and must be set to FALSE.


### -param EnableVirtualization [in]

A BOOLEAN value that specifies whether  virtualization should be enabled in the PCI configuration space of the network adapter.  If <i>EnableVirtualization</i> is TRUE, <b>NdisMEnableVirtualization</b> sets the <b>VF Enable</b> bit  of the SR-IOV Control member. <b>NdisMEnableVirtualization</b> clears this bit if <i>EnableVirtualization</i> is FALSE.


## -returns



<b>NdisMEnableVirtualization</b> can return one of the following status values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The virtualization operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The adapter or system does not support SR-IOV.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>EnableVirtualization</i> parameter is set to FALSE and the <i>NumVFs</i> parameter is set to a nonzero value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The virtualization operation failed.

<div class="alert"><b>Note</b>  The <b>NdisMEnableVirtualization</b> function fails if it is called to enable virtualization when virtualization is already enabled. The driver must first disable virtualization (by calling the function with the <b>EnableVirtualization</b> parameter set to FALSE) before the driver can reenable virtualization.</div>
<div> </div>
</td>
</tr>
</table>
 




## -remarks



PF miniport drivers call <b>NdisMEnableVirtualization</b> to configure the SR-IOV Extended Capability fields in the PCI configuration space. This call is used to enable or disable virtualization in the configuration space, and also to specify the number of VFs that should be exposed to the PCIe  fabric  by the network adapter.

When the PF miniport driver handles an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451815">OID_NIC_SWITCH_CREATE_SWITCH</a>, the driver calls <b>NdisMEnableVirtualization</b> to enable virtualization on the network adapter for the NIC switch. The driver does this by calling <b>NdisMEnableVirtualization</b> with the following parameter settings.



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="NumVFs"></a><a id="numvfs"></a><a id="NUMVFS"></a><i>NumVFs</i>

</td>
<td width="60%">
Set to the number of VFs to be enabled for the NIC switch.

</td>
</tr>
<tr>
<td width="40%">
<a id="EnableVirtualization"></a><a id="enablevirtualization"></a><a id="ENABLEVIRTUALIZATION"></a><i>EnableVirtualization</i>

</td>
<td width="60%">
Set to TRUE.

</td>
</tr>
</table>
 

When the PF miniport driver handles an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451817">OID_NIC_SWITCH_DELETE_SWITCH</a>, the driver calls <b>NdisMEnableVirtualization</b> to disable virtualization on the network adapter. The driver does this by calling <b>NdisMEnableVirtualization</b> with the following parameter settings:



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="NumVFs"></a><a id="numvfs"></a><a id="NUMVFS"></a><i>NumVFs</i>

</td>
<td width="60%">
Set to zero.

</td>
</tr>
<tr>
<td width="40%">
<a id="EnableVirtualization"></a><a id="enablevirtualization"></a><a id="ENABLEVIRTUALIZATION"></a><i>EnableVirtualization</i>

</td>
<td width="60%">
Set to FALSE.

</td>
</tr>
</table>
 

For more information on how to create a NIC switch, see <a href="https://msdn.microsoft.com/5A184EBD-95F4-4C11-AACD-49DF04578CA0">Creating a NIC Switch</a>.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

<h3><a id="Interfacing_to_a_Virtual_Bus_Driver"></a><a id="interfacing_to_a_virtual_bus_driver"></a><a id="INTERFACING_TO_A_VIRTUAL_BUS_DRIVER"></a>Interfacing to a Virtual Bus Driver</h3>
If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff544817">driver package</a>, its miniport driver must not call <b>NdisMEnableVirtualization</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451005">EnableVirtualization</a>. This function is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface that is supported by the underlying PCI bus driver. 

The VBD that runs in the Hyper-V parent partition's management operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the PCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_PCI_VIRTUALIZATION_INTERFACE.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451005">EnableVirtualization</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451817">OID_NIC_SWITCH_DELETE_SWITCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451815">OID_NIC_SWITCH_CREATE_SWITCH</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMEnableVirtualization function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

