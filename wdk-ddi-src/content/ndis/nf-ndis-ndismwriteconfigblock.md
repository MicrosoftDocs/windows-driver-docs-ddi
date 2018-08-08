---
UID: NF:ndis.NdisMWriteConfigBlock
title: NdisMWriteConfigBlock function
author: windows-driver-content
description: A miniport driver for a PCI Express (PCIe) Virtual Function (VF) calls the NdisMWriteConfigBlock function to write data to a VF configuration block.
old-location: netvista\ndismwriteconfigblock.htm
tech.root: netvista
ms.assetid: de7f651b-9847-41e9-9f52-71c2365bac44
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisMWriteConfigBlock, NdisMWriteConfigBlock function [Network Drivers Starting with Windows Vista], ndis/NdisMWriteConfigBlock, netvista.ndismwriteconfigblock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
-	NdisMWriteConfigBlock
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMWriteConfigBlock function


## -description


A miniport driver for a PCI Express (PCIe) Virtual Function (VF) calls the <b>NdisMWriteConfigBlock</b> function to write data to a VF configuration block. Write operations on a VF configuration block are handled by the miniport driver of the network adapter's PCIe Physical Function (PF).
<div class="alert"><b>Note</b>  <b>NdisMWriteConfigBlock</b> must only be called by the miniport driver for a network adapter's VF.</div><div> </div>

## -parameters




### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param BlockId [in]

A ULONG value that specifies the identifier of the configuration block to be written to. This identifier is proprietary to the independent hardware vendor (IHV) and is used only by the miniport drivers for the PF and VF on the network adapter.



### -param Buffer [in]

A pointer to a caller-allocated buffer that contains the configuration data to be written.


### -param Length [in]

The number of bytes to write to the configuration block.


## -returns



<b>NdisMWriteConfigBlock</b> can return one of the following status values.

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
The write operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The write operation failed.

</td>
</tr>
</table>
 




## -remarks



The VF miniport driver  calls <b>NdisMWriteConfigBlock</b> to initiate a backchannel write request of VF configuration data by the PF miniport driver. Once notified of this request, the PF driver writes the data to the specified VF configuration block.

A VF configuration block is used for backchannel communication between the PF and VF miniport drivers. The IHV can define one or more VF configuration blocks for the device. Each VF configuration block has an IHV-defined format, length,  and block ID.

<div class="alert"><b>Note</b>  Data from each VF configuration block is  used only by the PF and VF miniport drivers.

</div>
<div> </div>
For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="https://msdn.microsoft.com/66D40452-1286-449E-BD6B-AFAD466E03A1">SR-IOV PF/VF Backchannel Communication</a>.

<h3><a id="Interfacing_to_a_Virtual_Bus_Driver"></a><a id="interfacing_to_a_virtual_bus_driver"></a><a id="INTERFACING_TO_A_VIRTUAL_BUS_DRIVER"></a>Interfacing to a Virtual Bus Driver</h3>
If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff544817">driver package</a>, its miniport driver must not call <b>NdisMWriteConfigBlock</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451609">WriteVfConfigBlock</a>. This function is exposed from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a> interface that is supported by the underlying virtual PCI (VPCI) bus driver.

The VBD that runs in a Hyper-V child partition's guest operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a> interface by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the VPCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_VPCI_INTERFACE_STANDARD.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451609">WriteVfConfigBlock</a>
 

 

