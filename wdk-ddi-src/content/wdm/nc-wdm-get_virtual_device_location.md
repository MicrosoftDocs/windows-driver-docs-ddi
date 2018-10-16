---
UID: NC:wdm.GET_VIRTUAL_DEVICE_LOCATION
title: GET_VIRTUAL_DEVICE_LOCATION
author: windows-driver-content
description: The GetLocation routine returns the device location of a PCI Express (PCIe) virtual function (VF) on a PCI bus. A device that supports the single root I/O virtualization (SR-IOV) interface can expose one or more VFs on the PCI bus.
old-location: pci\getlocation.htm
tech.root: PCI
ms.assetid: A08294EC-7A1B-4A2D-A425-D19ABDCB9DCA
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: GET_VIRTUAL_DEVICE_LOCATION, GetLocation, GetLocation routine, PCI.getlocation, wdm/GetLocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows Server.
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
-	GetLocation
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# GET_VIRTUAL_DEVICE_LOCATION callback


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451128">GetLocation</a> routine returns the device location of a PCI Express (PCIe) virtual function (VF) on a PCI bus. A device that supports the single root I/O virtualization (SR-IOV) interface can expose one or more VFs on the PCI bus.


## -prototype


```cpp
GET_VIRTUAL_DEVICE_LOCATION GetLocation;

NTSTATUS GetLocation(
  _Inout_ PVOID   Context,
  _In_    USHORT  VirtualFunction,
  _Out_   PUINT16 SegmentNumber,
  _Out_   PUINT8  BusNumber,
  _Out_   PUINT8  FunctionNumber
)
{ ... }
```


## -parameters




### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param VirtualFunction [in]

A zero-based value that specifies the VF on the device for  which the device location is returned


### -param SegmentNumber [out]

A pointer to a caller-supplied variable in which this routine returns a UINT16 value for the current PCI segment number. This value specifies the group of PCI buses on which the device is attached.




### -param BusNumber [out]

A pointer to a caller-supplied variable in which this routine returns a UINT8 value. This value specifies the current PCI bus number on which the device is attached.




### -param FunctionNumber [out]

A pointer to a caller-supplied variable in which this routine returns a UINT8 value.  This value contains the function number for the specified VF on the PCI bus.


## -returns



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451128">GetLocation</a> routine returns one of the following NTSTATUS values:

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>VirtualFunction</i> parameter is larger than the value of the <b>TotalVFs</b> member of the SR-IOV Extended Capability structure for the device.

</td>
</tr>
</table>
 




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451128">GetLocation</a> routine returns the current device location of a VF  in the PCIe hierarchy. This information is necessary for a virtualization system that is using an I/O memory management unit (IOMMU) to route traffic to or from the device.

Upon a successful return from a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451128">GetLocation</a> routine, the <i>FunctionNumber</i> parameter contains a value that represents the function number for the specified VF on the PCI bus. This value is based on the Alternative Routing Interpretation (ARI) option of the PCI Express 3.0 specification.  ARI treats a PCIe bus as a single device with an 8-bit function space, which allows for 256 functions on the bus.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451128">GetLocation</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface.

<div class="alert"><b>Important</b>  The PCI bus number on which the VF is located can change. We do not recommend that drivers store the device location for a VF in nonvolatile storage such as the registry.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<b></b>



 

 


