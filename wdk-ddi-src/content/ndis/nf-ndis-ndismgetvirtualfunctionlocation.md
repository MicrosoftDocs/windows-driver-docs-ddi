---
UID: NF:ndis.NdisMGetVirtualFunctionLocation
title: NdisMGetVirtualFunctionLocation function
author: windows-driver-content
description: A miniport driver calls the NdisMGetVirtualFunctionLocation function to query the device location of a PCI Express (PCIe) Virtual Function (VF) on a PCI bus. The driver uses the device location to construct the PCIe Requestor ID (RID) for the VF.
old-location: netvista\ndismgetvirtualfunctionlocation.htm
old-project: netvista
ms.assetid: 772A7763-67C0-4218-8C5F-23972475D2C9
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisMGetVirtualFunctionLocation, NdisMGetVirtualFunctionLocation function [Network Drivers Starting with Windows Vista], ndis/NdisMGetVirtualFunctionLocation, netvista.ndismgetvirtualfunctionlocation
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
-	NdisMGetVirtualFunctionLocation
product: Windows
targetos: Windows
req.typenames: 
---

# NdisMGetVirtualFunctionLocation function


## -description


A miniport driver calls the <b>NdisMGetVirtualFunctionLocation</b> function to query the device location of a PCI Express (PCIe) Virtual Function (VF) on a  PCI bus. The driver uses the device location to construct the PCIe Requestor ID (RID) for the VF.
<div class="alert"><b>Note</b>  <b>NdisMGetVirtualFunctionLocation</b> must only be called by the miniport driver for the network adapter's PCIe Physical Function (PF).</div><div> </div>

## -parameters




### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param VFId [in]

The identifier of the VF for which the device location is returned.


### -param SegmentNumber [out]

A pointer to a caller-supplied variable in which this function returns a USHORT value for the current PCI segment number. This value specifies the group of PCI buses on which the device is attached.


### -param BusNumber [out]

A pointer to a caller-supplied variable in which this function returns a UCHAR value. This value specifies the current PCI bus number on which the device is attached.


### -param FunctionNumber [out]

A pointer to a caller-supplied variable in which this function returns a UCHAR value. This value specifies the function number of a logical device on the device.


## -returns




     None.




## -remarks



 When  it handles a method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>, the PF miniport driver must return the RID for the VF that the driver has successfully allocated on the network adapter. The driver generates the RID in the following way:<ol>
<li>
The driver first calls the  <b>NdisMGetVirtualFunctionLocation</b> function to obtain the bus-related location information for the VF.

</li>
<li>
The driver then calls the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451557">NDIS_MAKE_RID</a> macro with the bus-related location information to generate the RID.

</li>
</ol>


For more information on how to allocate VF resources, see <a href="https://msdn.microsoft.com/352E12EC-FAF0-4566-8632-B6DA97ACCAD9">Virtual Function Initialization Sequence</a>.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

<h3><a id="Interfacing_to_a_Virtual_Bus_Driver"></a><a id="interfacing_to_a_virtual_bus_driver"></a><a id="INTERFACING_TO_A_VIRTUAL_BUS_DRIVER"></a>Interfacing to a Virtual Bus Driver</h3>
If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff544817">driver package</a>, its miniport driver must not call <b>NdisMGetVirtualFunctionLocation</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451128">GetLocation</a>. This function is exposed from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface supported by the underlying PCI bus driver.

The VBD that runs in the Hyper-V parent partition's management operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the PCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_PCI_VIRTUALIZATION_INTERFACE.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451128">GetLocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451557">NDIS_MAKE_RID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>
 

 

