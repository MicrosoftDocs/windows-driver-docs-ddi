---
UID: NC:wdm.GET_VIRTUAL_DEVICE_RESOURCES
title: GET_VIRTUAL_DEVICE_RESOURCES
description: The GetResources routine returns the resources that the PCI Express (PCIe) physical function (PF) requires in order to enable virtualization on a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\getresources.htm
tech.root: PCI
ms.assetid: 4F29E9BD-F534-45EC-99C3-F006A0E03B31
ms.date: 02/24/2018
ms.keywords: GET_VIRTUAL_DEVICE_RESOURCES, GetResources, GetResources routine, PCI.getresources, wdm/GetResources
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
-	GetResources
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# GET_VIRTUAL_DEVICE_RESOURCES callback


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451131">GetResources</a> routine returns the resources that the PCI Express (PCIe) physical function (PF) requires in order to enable virtualization on a device that supports the single root I/O virtualization (SR-IOV) interface.


## -prototype


```cpp
GET_VIRTUAL_DEVICE_RESOURCES GetResources;

VOID GetResources(
  _Inout_ PVOID  Context,
  _Out_   PUINT8 CapturedBusNumbers
)
{ ... }
```


## -parameters




### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param CapturedBusNumbers [out]

A pointer to a caller-supplied variable in which this routine returns a UINT8 value. This value specifies the number of PCIe buses that have been captured for use by the SR-IOV PF of the device.


## -returns



This routine does not return a value.




## -remarks



A PCIe device typically consumes resources on a single PCI bus.  The PCI driver assigns a device to a PCI bus by writing the bus number into the Secondary Bus Number register and Subordinate Bus Number register in the upstream bridge port. This port is a PCI-to-PCI bridge within a PCIe root port or a PCIe switch port.

A device that supports the SR-IOV interface may create more virtual functions than can be accommodated on the PCI bus on which the device is connected.  In these situations, the upstream bridge port must be configured to capture one or more unused PCI buses.  This is done by writing a larger value to the port's Subordinate Bus Number register.

A device that supports the SR-IOV interface  must capture PCI buses if at least one of the following is true:
<ul>
<li>
The device has more than eight total functions (PFs and VFs) and the device does not support the Alternative Routing Interpretation (ARI) option of the PCI Express 3.0 specification.


</li>
<li>
The device supports ARI and has more than eight total functions, but the upstream bridge port does not support ARI.


</li>
<li>
The device supports ARI and has more than 256 functions, and the upstream bridge port does  support ARI.

</li>
</ul>
<div class="alert"><b>Note</b>  Regardless of ARI support, each captured bus can support 256 functions.</div>
<div> </div>


If the device needs more PCIe Requestor IDs (RIDs) in order to enable all  of its VFs, the PCI bus driver does the following:<ol>
<li>
Writes the device’s bus number into the PCIe Secondary Bus Number register.

</li>
<li>
Writes a value that is larger than the device’s bus number into the PCIe Subordinate Bus Number register.

</li>
</ol>The difference between these two register values represents the number of captured bus numbers.



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451131">GetResources</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<b></b>



 

 


