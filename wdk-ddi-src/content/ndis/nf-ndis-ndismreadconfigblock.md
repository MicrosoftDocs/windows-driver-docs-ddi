---
UID: NF:ndis.NdisMReadConfigBlock
title: NdisMReadConfigBlock function
author: windows-driver-content
description: A miniport driver for a PCI Express (PCIe) Virtual Function (VF) calls the NdisMReadConfigBlock function to read data from a VF configuration block.
old-location: netvista\ndismreadconfigblock.htm
old-project: netvista
ms.assetid: a4b5e669-7abb-4c60-b2dc-249103d0b20c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMReadConfigBlock, NdisMReadConfigBlock function [Network Drivers Starting with Windows Vista], ndis/NdisMReadConfigBlock, netvista.ndismreadconfigblock
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMReadConfigBlock
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMReadConfigBlock function


## -description


A miniport driver for a PCI Express (PCIe) Virtual Function (VF) calls the <b>NdisMReadConfigBlock</b> function to read data from a VF configuration block.  Read operations for a VF configuration block are handled by the miniport driver of the network adapter's PCIe Physical Function (PF).
<div class="alert"><b>Note</b>  <b>NdisMReadConfigBlock</b> must only be called by the VF miniport driver.</div><div> </div>

## -parameters




### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param BlockId [in]

A ULONG value that specifies the identifier of the VF configuration block to be read. This identifier is proprietary to the independent hardware vendor (IHV) and is used only by the PF and VF miniport drivers.



### -param Buffer [out]

A pointer to a caller-allocated buffer that will contain the requested configuration data.


### -param Length [in]

The number of bytes to be read from the VF configuration block.


## -returns



<b>NdisMReadConfigBlock</b> can return one of the following status values:

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
The query operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The query operation failed.

</td>
</tr>
</table>
 




## -remarks



The VF miniport driver  calls <b>NdisMReadConfigBlock</b> to initiate a backchannel read request of VF configuration data by the PF miniport driver. Once notified of this request, the PF driver returns the data from the specified VF configuration block.

A VF configuration block is used for backchannel communication between the PF and VF miniport drivers. The IHV can define one or more VF configuration blocks for the device. Each VF configuration block has an IHV-defined format, length,  and block ID.

<div class="alert"><b>Note</b>  Data from each VF configuration block is  used only by the PF and VF miniport drivers.

</div>
<div> </div>
For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="https://msdn.microsoft.com/66D40452-1286-449E-BD6B-AFAD466E03A1">SR-IOV PF/VF Backchannel Communication</a>.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

<h3><a id="Interfacing_to_a_Virtual_Bus_Driver"></a><a id="interfacing_to_a_virtual_bus_driver"></a><a id="INTERFACING_TO_A_VIRTUAL_BUS_DRIVER"></a>Interfacing to a Virtual Bus Driver</h3>
If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff544817">driver package</a>, its miniport driver must not call <b>NdisMReadConfigBlock</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="https://msdn.microsoft.com/library/windows/hardware/hh439637">ReadVfConfigBlock</a>. This function is exposed from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a> interface that is supported by the underlying virtual PCI (VPCI) bus driver.

The VBD that runs in a Hyper-V child partition's guest operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a> interface by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the VPCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_VPCI_INTERFACE_STANDARD.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439637">ReadVfConfigBlock</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMReadConfigBlock function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
