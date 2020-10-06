---
UID: NF:ndis.NdisMSetVirtualFunctionBusData
title: NdisMSetVirtualFunctionBusData function (ndis.h)
description: A miniport driver calls the NdisMSetVirtualFunctionBusData function to write data to the PCI Express (PCIe) configuration space of a Virtual Function (VF) on the network adapter.
old-location: netvista\ndismsetvirtualfunctionbusdata.htm
tech.root: netvista
ms.assetid: 74c6789e-22a6-42e9-bc14-8b9f93da668b
ms.date: 05/02/2018
keywords: ["NdisMSetVirtualFunctionBusData function"]
ms.keywords: NdisMSetVirtualFunctionBusData, NdisMSetVirtualFunctionBusData function [Network Drivers Starting with Windows Vista], ndis/NdisMSetVirtualFunctionBusData, netvista.ndismsetvirtualfunctionbusdata
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMSetVirtualFunctionBusData
 - ndis/NdisMSetVirtualFunctionBusData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMSetVirtualFunctionBusData
---

# NdisMSetVirtualFunctionBusData function


## -description

A miniport driver calls the <b>NdisMSetVirtualFunctionBusData</b> function to write data to the PCI  Express (PCIe) configuration space of a Virtual Function (VF) on the network adapter. 
<div class="alert"><b>Note</b>  <b>NdisMGetVirtualFunctionBusData</b> must only be called by the miniport driver for the network adapter's PCIe Physical Function (PF).</div><div> </div>

## -parameters

### -param NdisMiniportHandle 

[in]
The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.

### -param VFId 

[in]
The identifier of the VF to which data is written to its  PCI configuration space.

### -param Buffer 

[in]
A pointer to a buffer that contains the data to be written to the PCI configuration space.

### -param Offset 

[in]
The offset, in units of bytes, in the PCI configuration space to which data is written.

### -param Length 

[in]
The length, in units of bytes, of the data to be written.

## -returns

<b>NdisMSetVirtualFunctionBusData</b> returns the number of bytes written to the PCI configuration space. If the write operation fails, <b>NdisMSetVirtualFunctionBusData</b> returns zero.

## -remarks

The PF miniport driver typically calls <b>NdisMSetVirtualFunctionBusData</b> when it handles an OID method request of  <a href="/windows-hardware/drivers/network/oid-sriov-write-vf-config-space">OID_SRIOV_WRITE_VF_CONFIG_SPACE</a>.  
However, the driver can call this function any time after virtualization has been enabled on the network adapter through a call to <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismenablevirtualization">NdisMEnableVirtualization</a>.

For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="/windows-hardware/drivers/network/sr-iov-pf-vf-backchannel-communication">SR-IOV PF/VF Backchannel Communication</a>.

For more information about the SR-IOV interface, see 	<a href="/windows-hardware/drivers/network/overview-of-single-root-i-o-virtualization--sr-iov-">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

<h3><a id="Interfacing_to_a_Virtual_Bus_Driver"></a><a id="interfacing_to_a_virtual_bus_driver"></a><a id="INTERFACING_TO_A_VIRTUAL_BUS_DRIVER"></a>Interfacing to a Virtual Bus Driver</h3>
If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="/previous-versions/windows/hardware/difxapi/driverpackagepreinstall">driver package</a>, its miniport driver must not call <b>NdisMSetVirtualFunctionBusData</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-set_virtual_device_data">SetVirtualFunctionData</a>. This function is exposed from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface that is supported by the underlying PCI bus driver.

The VBD that runs in the Hyper-V parent partition's management operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface by issuing an <a href="/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the PCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_PCI_VIRTUALIZATION_INTERFACE.

## -see-also

<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismenablevirtualization">NdisMEnableVirtualization</a>



<a href="/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>



<a href="/windows-hardware/drivers/network/oid-sriov-write-vf-config-space">OID_SRIOV_WRITE_VF_CONFIG_SPACE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-set_virtual_device_data">SetVirtualFunctionData</a>