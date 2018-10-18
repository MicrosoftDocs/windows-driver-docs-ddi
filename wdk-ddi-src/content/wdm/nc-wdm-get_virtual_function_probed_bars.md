---
UID: NC:wdm.GET_VIRTUAL_FUNCTION_PROBED_BARS
title: GET_VIRTUAL_FUNCTION_PROBED_BARS
author: windows-driver-content
description: The GetVirtualFunctionProbedBars routine returns the values of the PCI Express (PCIe) Base Address Registers (BARs) of a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\getvirtualfunctionprobedbars.htm
tech.root: PCI
ms.assetid: 02A86A3E-D543-4F0F-9985-7D42F381F8F1
ms.date: 2/24/2018
ms.keywords: GET_VIRTUAL_FUNCTION_PROBED_BARS, GetVirtualFunctionProbedBars, GetVirtualFunctionProbedBars routine, PCI.getvirtualfunctionprobedbars, wdm/GetVirtualFunctionProbedBars
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	GetVirtualFunctionProbedBars
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# GET_VIRTUAL_FUNCTION_PROBED_BARS callback


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine returns the values of the PCI Express (PCIe) Base Address Registers (BARs) of a device that supports the single root I/O virtualization (SR-IOV) interface.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> returns the BAR values that were reported by the device after a query that was performed by the PCI bus driver. This query determines the memory or I/O address space that is required by the device.


## -prototype


```cpp
GET_VIRTUAL_FUNCTION_PROBED_BARS GetVirtualFunctionProbedBars;

NTSTATUS GetVirtualFunctionProbedBars(
  _Inout_ PVOID  Context,
  _Out_   PULONG BaseRegisterValues
)
{ ... }
```


## -parameters




### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param BaseRegisterValues [out]

A pointer to an array of ULONG values. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine returns a value for each BAR of the device.

<div class="alert"><b>Note</b>  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> returns a maximum of <b>PCI_TYPE0_ADDRESSES</b> values within this array.
</div>
<div> </div>

## -returns



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The device does not support the SR-IOV interface.

</td>
</tr>
</table>
 




## -remarks



The PCI bus driver. which runs in the management operating system  of the Hyper-V parent partition, queries the memory or I/O address space requirements of each  BAR of the device. The PCI bus driver performs this query when the it first detects the adapter on the bus.

Through this BAR query, the PCI bus driver determines the following:

<ul>
<li>
Whether a BAR is supported by the device.

</li>
<li>
If a BAR is supported, how much memory or I/O
address space is required for the BAR.

</li>
</ul>
The PCI driver performs this BAR query as follows:

<ol>
<li>
The PCI bus driver writes 0xFFFFFFFF to a BAR.

</li>
<li>
The PCI bus driver reads the BAR to determine the memory or address space that the device requires. A value of zero indicates that the device does not support the BAR.

</li>
</ol>
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface.

The following notes apply to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine:

<ul>
<li>
The SR-IOV interface does not require that the BARs of a PCIe VF comply with the protocol for determining the size of the memory block or I/O address space of a BAR. Therefore, the virtual PCI (VPCI) driver, which runs in the guest operating system, determines the size by using the equivalent size from the BARs on the physical device. The VPCI driver obtains this information by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine.


</li>
<li>
	The VPCI driver requires the size of the memory or I/O
address space for each BAR after the physical device has started. At that point, the PCI driver cannot perform a BAR query  on the device without altering the current value of the BAR. Therefore, when the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine is called by the VPCI driver, the PCI driver returns the BAR information that it obtained during the BAR query. The PCI driver performed this query when the device was first detected on the bus.

</li>
</ul>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<b></b>



 

 


