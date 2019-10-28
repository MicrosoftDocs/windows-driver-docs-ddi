---
UID: NF:ndis.NdisMGetVirtualFunctionBusData
title: NdisMGetVirtualFunctionBusData function (ndis.h)
description: A miniport driver calls the NdisMGetVirtualFunctionBusData function to read data from the PCI Express (PCIe) configuration space of a specified Virtual Function (VF) on the network adapter.
old-location: netvista\ndismgetvirtualfunctionbusdata.htm
tech.root: netvista
ms.assetid: 15e2e1f4-6039-4588-a7ba-bd8aa6b78839
ms.date: 05/02/2018
ms.keywords: NdisMGetVirtualFunctionBusData, NdisMGetVirtualFunctionBusData function [Network Drivers Starting with Windows Vista], ndis/NdisMGetVirtualFunctionBusData, netvista.ndismgetvirtualfunctionbusdata
ms.topic: function
f1_keywords:
 - "ndis/NdisMGetVirtualFunctionBusData"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMGetVirtualFunctionBusData
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMGetVirtualFunctionBusData function


## -description


A miniport driver calls the <b>NdisMGetVirtualFunctionBusData</b> function to read data from the PCI  Express (PCIe) configuration space of a specified Virtual Function (VF) on the network adapter. 
<div class="alert"><b>Note</b>  <b>NdisMGetVirtualFunctionBusData</b> must only be called by the miniport driver for the network adapter's PCIe Physical Function (PF).   
</div><div> </div>

## -parameters




### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.


### -param VFId [in]

The identifier of the VF from which the data from the PCI configuration space is returned.


### -param Buffer [out]

A pointer to a buffer that receives the data that is read from the VF's PCI configuration space.


### -param Offset [in]

The offset, in units of bytes, in the VF's PCI configuration space from which data is read.




### -param Length [in]

The length, in units of bytes, of the data to be read.

<div class="alert"><b>Note</b>  The size of the buffer referenced by <i>Buffer</i> must be at least as large as the value of the <i>Length</i> parameter.</div>
<div> </div>

## -returns



<b>NdisMGetVirtualFunctionBusData</b> returns the number of bytes that are read from the PCI configuration space. If the read operation fails, <b>NdisMGetVirtualFunctionBusData</b> returns zero.




## -remarks



The PF miniport driver typically calls <b>NdisMGetVirtualFunctionBusData</b> when it handles an OID method request of  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-read-vf-config-space">OID_SRIOV_READ_VF_CONFIG_SPACE</a>.  
However, the driver can call this function any time after virtualization has been enabled on the network adapter through a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismenablevirtualization">NdisMEnableVirtualization</a>.

For more information on how to query the VF's PCI configuration space, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/querying-the-pci-configuration-space-for-a-virtual-function">Querying the PCI Configuration Space for a Virtual Function</a>.

For more information about the SR-IOV interface, see 	<a href="https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-single-root-i-o-virtualization--sr-iov-">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

<h3><a id="Interfacing_to_a_Virtual_Bus_Driver"></a><a id="interfacing_to_a_virtual_bus_driver"></a><a id="INTERFACING_TO_A_VIRTUAL_BUS_DRIVER"></a>Interfacing to a Virtual Bus Driver</h3>
If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="https://docs.microsoft.com/previous-versions/windows/hardware/difxapi/driverpackagepreinstall">driver package</a>, its miniport driver must not call <b>NdisMGetVirtualFunctionBusData</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data">GetVirtualFunctionData</a>. This function is exposed from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface that is supported by the underlying PCI bus driver.

The VBD that runs in the Hyper-V parent partition's management operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface by issuing an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the PCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_PCI_VIRTUALIZATION_INTERFACE.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data">GetVirtualFunctionData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismenablevirtualization">NdisMEnableVirtualization</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-read-vf-config-space">OID_SRIOV_READ_VF_CONFIG_SPACE</a>
 

 

