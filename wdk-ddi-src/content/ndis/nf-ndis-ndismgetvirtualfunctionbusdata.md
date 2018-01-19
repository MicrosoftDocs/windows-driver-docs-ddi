---
UID: NF:ndis.NdisMGetVirtualFunctionBusData
title: NdisMGetVirtualFunctionBusData function
author: windows-driver-content
description: A miniport driver calls the NdisMGetVirtualFunctionBusData function to read data from the PCI Express (PCIe) configuration space of a specified Virtual Function (VF) on the network adapter.
old-location: netvista\ndismgetvirtualfunctionbusdata.htm
old-project: netvista
ms.assetid: 15e2e1f4-6039-4588-a7ba-bd8aa6b78839
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMGetVirtualFunctionBusData
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
req.alt-api: NdisMGetVirtualFunctionBusData
req.alt-loc: ndis.lib,ndis.dll
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMGetVirtualFunctionBusData function



## -description
A miniport driver calls the <b>NdisMGetVirtualFunctionBusData</b> function to read data from the PCI  Express (PCIe) configuration space of a specified Virtual Function (VF) on the network adapter. 



## -syntax

````
ULONG NdisMGetVirtualFunctionBusData(
  _In_  NDIS_HANDLE            NdisMiniportHandle,
  _In_  NDIS_SRIOV_FUNCTION_ID VFId,
  _Out_ PVOID                  Buffer,
  _In_  ULONG                  Offset,
  _In_  ULONG                  Length
);
````


## -parameters

### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


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
The PF miniport driver typically calls <b>NdisMGetVirtualFunctionBusData</b> when it handles an OID method request of  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451879">OID_SRIOV_READ_VF_CONFIG_SPACE</a>.  
However, the driver can call this function any time after virtualization has been enabled on the network adapter through a call to <a href="..\ndis\nf-ndis-ndismenablevirtualization.md">NdisMEnableVirtualization</a>.

For more information on how to query the VF's PCI configuration space, see <a href="https://msdn.microsoft.com/FFE7C946-4406-46A5-A9A7-CD0E2756C98E">Querying the PCI Configuration Space for a Virtual Function</a>.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff544817">driver package</a>, its miniport driver must not call <b>NdisMGetVirtualFunctionBusData</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451137">GetVirtualFunctionData</a>. This function is exposed from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface that is supported by the underlying PCI bus driver.

The VBD that runs in the Hyper-V parent partition's management operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the PCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_PCI_VIRTUALIZATION_INTERFACE.


## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451137">GetVirtualFunctionData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismenablevirtualization.md">NdisMEnableVirtualization</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451879">OID_SRIOV_READ_VF_CONFIG_SPACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMGetVirtualFunctionBusData function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

