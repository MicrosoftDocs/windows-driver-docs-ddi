---
UID: NF:ndis.NdisMQueryProbedBars
title: NdisMQueryProbedBars function
author: windows-driver-content
description: A miniport driver calls the NdisMQueryProbedBars function to obtain the values of a network adapter's PCI Express (PCIe) Base Address Registers (BARs).
old-location: netvista\ndismqueryprobedbars.htm
old-project: netvista
ms.assetid: 39deba08-3ff0-4037-b530-0cb4a01fc758
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NdisMQueryProbedBars, NdisMQueryProbedBars function [Network Drivers Starting with Windows Vista], ndis/NdisMQueryProbedBars, netvista.ndismqueryprobedbars
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
-	NdisMQueryProbedBars
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMQueryProbedBars function


## -description


A miniport driver calls the <b>NdisMQueryProbedBars</b> function to obtain the values of a network adapter's PCI Express (PCIe) Base Address Registers (BARs). This function returns the BAR values that were reported by the network adapter following a query performed by the PCI bus driver. This query determines the memory or I/O address space that is required by the network adapter. 
<div class="alert"><b>Note</b>  <b>NdisMQueryProbedBars</b> must only be called by the miniport driver for the network adapter's PCIe Physical Function (PF).</div><div> </div>

## -syntax


````
NDIS_STATUS NdisMQueryProbedBars(
  _In_  NDIS_HANDLE NdisMiniportHandle,
  _Out_ PULONG      BaseRegisterValues
);
````


## -parameters




### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


### -param BaseRegisterValues [out]

A pointer to an array of ULONG values. The array  contains a ULONG value for each BAR of the PCIe network adapter.

<div class="alert"><b>Note</b>  <b>NdisMQueryProbedBars</b> returns a maximum of PCI_TYPE0_ADDRESSES values within this array.
</div>
<div> </div>

## -returns



<b>NdisMQueryProbedBars</b> can return one of the following status values.

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



The PCI bus driver, which runs in the management operating system  of the Hyper-V parent partition, queries the memory or I/O address space requirements of each  PCI Base Address Register (BAR) of the network adapter. The PCI bus driver performs this query when it first detects the adapter on the bus. 

Through this PCI BAR query, the PCI bus driver determines the following:

<ul>
<li>
Whether a PCI BAR is supported by the network adapter.

</li>
<li>
If a BAR is supported, how much memory or I/O
address space is required for the BAR.

</li>
</ul>
The virtual PCI (VPCI) bus driver runs in the guest operating system of a Hyper-V child partition. When a PCI Express (PCIe) Virtual Function (VF) is attached to the child partition, the VPCI bus driver will expose a virtual network adapter for the VF (<i>VF network adapter</i>). Before it does this, the VPCI bus driver must perform a PCI BAR query to determine the required memory or address space that is required by the VF network adapter.

Because access to the PCI configuration space is a privileged operation, it can only be performed by components that run in the management operating system of a Hyper-V parent partition. When the VPCI bus driver queries the PCI BARs, NDIS issues an object identifier (OID) query request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451870">OID_SRIOV_PROBED_BARS</a> to the PF miniport driver. The results returned by this OID query request are forwarded to the VPCI bus driver so that it can determine how much memory address space would be needed by the VF network adapter. 

During the handling of this OID request, the driver can call <b>NdisMQueryProbedBars</b> to obtain the values returned from the BAR query performed by the PCI driver.


For more information on how to query PCI BAR registers for a VF, see <a href="https://msdn.microsoft.com/99C2BF61-E87E-4C3B-BE7E-C16B5318EC1A">Querying the PCI Base Address Registers of a Virtual Function</a>.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

<h3><a id="Interfacing_to_a_Virtual_Bus_Driver"></a><a id="interfacing_to_a_virtual_bus_driver"></a><a id="INTERFACING_TO_A_VIRTUAL_BUS_DRIVER"></a>Interfacing to a Virtual Bus Driver</h3>
If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff544817">driver package</a>, its miniport driver must not call <b>NdisMQueryProbedBars</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a>. This function is exposed from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface that is supported by the underlying PCI bus driver.

The VBD that runs in the Hyper-V parent partition's management operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the PCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_PCI_VIRTUALIZATION_INTERFACE.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451870">OID_SRIOV_PROBED_BARS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMQueryProbedBars function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

