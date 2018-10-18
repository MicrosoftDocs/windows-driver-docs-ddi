---
UID: NS:miniport._PCI_EXPRESS_CAPABILITY
title: "_PCI_EXPRESS_CAPABILITY"
author: windows-driver-content
description: The PCI_EXPRESS_CAPABILITY structure describes a PCI Express (PCIe) capability structure.
old-location: pci\pci_express_capability.htm
tech.root: PCI
ms.assetid: f1faf319-95de-41f8-b32c-927ff4bb17ea
ms.date: 2/24/2018
ms.keywords: "*PPCI_EXPRESS_CAPABILITY, PCI.pci_express_capability, PCI_EXPRESS_CAPABILITY, PCI_EXPRESS_CAPABILITY structure [Buses], PPCI_EXPRESS_CAPABILITY, PPCI_EXPRESS_CAPABILITY structure pointer [Buses], _PCI_EXPRESS_CAPABILITY, ntddk/PCI_EXPRESS_CAPABILITY, ntddk/PPCI_EXPRESS_CAPABILITY, pci_struct_9c629781-bcee-486d-bab3-5d5b7441ac72.xml"
ms.topic: struct
req.header: miniport.h
req.include-header: Ntddk.h, Miniport.h
req.target-type: Windows
req.target-min-winverclnt:
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PCI_EXPRESS_CAPABILITY
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_CAPABILITY, *PPCI_EXPRESS_CAPABILITY
---

# _PCI_EXPRESS_CAPABILITY structure


## -description


The PCI_EXPRESS_CAPABILITY structure describes a PCI Express (PCIe) capability structure.


## -syntax


```cpp
typedef struct _PCI_EXPRESS_CAPABILITY {
  PCI_CAPABILITIES_HEADER                  Header;
  PCI_EXPRESS_CAPABILITIES_REGISTER        ExpressCapabilities;
  PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER DeviceCapabilities;
  PCI_EXPRESS_DEVICE_CONTROL_REGISTER      DeviceControl;
  PCI_EXPRESS_DEVICE_STATUS_REGISTER       DeviceStatus;
  PCI_EXPRESS_LINK_CAPABILITIES_REGISTER   LinkCapabilities;
  PCI_EXPRESS_LINK_CONTROL_REGISTER        LinkControl;
  PCI_EXPRESS_LINK_STATUS_REGISTER         LinkStatus;
  PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER   SlotCapabilities;
  PCI_EXPRESS_SLOT_CONTROL_REGISTER        SlotControl;
  PCI_EXPRESS_SLOT_STATUS_REGISTER         SlotStatus;
  PCI_EXPRESS_ROOT_CONTROL_REGISTER        RootControl;
  PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER   RootCapabilities;
  PCI_EXPRESS_ROOT_STATUS_REGISTER         RootStatus;
} PCI_EXPRESS_CAPABILITY, *PPCI_EXPRESS_CAPABILITY;
```


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a> structure that describes the PCI capabilities header of the PCIe capability structure.


### -field ExpressCapabilities

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537459">PCI_EXPRESS_CAPABILITIES_REGISTER</a> structure that describes the PCIe capabilities register of the PCIe capability structure.


### -field DeviceCapabilities

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537463">PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER</a> structure that describes the PCIe device capabilities register of the PCIe capability structure.


### -field DeviceControl

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537464">PCI_EXPRESS_DEVICE_CONTROL_REGISTER</a> structure that describes the PCIe device control register of the PCIe capability structure.


### -field DeviceStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537465">PCI_EXPRESS_DEVICE_STATUS_REGISTER</a> structure that describes the PCIe device status register of the PCIe capability structure.


### -field LinkCapabilities

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537468">PCI_EXPRESS_LINK_CAPABILITIES_REGISTER</a> structure that describes the PCIe link capabilities register of the PCIe capability structure.


### -field LinkControl

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537469">PCI_EXPRESS_LINK_CONTROL_REGISTER</a> structure that describes the PCIe link control register of the PCIe capability structure.


### -field LinkStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537470">PCI_EXPRESS_LINK_STATUS_REGISTER</a> structure that describes the PCIe link status register of the PCIe capability structure.


### -field SlotCapabilities

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537560">PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER</a> structure that describes the PCIe slot capabilities register of the PCIe capability structure.


### -field SlotControl

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537562">PCI_EXPRESS_SLOT_CONTROL_REGISTER</a> structure that describes the PCIe slot control register of the PCIe capability structure.


### -field SlotStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537564">PCI_EXPRESS_SLOT_STATUS_REGISTER</a> structure that describes the PCIe slot status register of the PCIe capability structure.


### -field RootControl

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537474">PCI_EXPRESS_ROOT_CONTROL_REGISTER</a> structure that describes the PCIe root control register of the PCIe capability structure.


### -field RootCapabilities

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537473">PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER</a> structure that describes the PCIe root capabilities register of the PCIe capability structure.


### -field RootStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537477">PCI_EXPRESS_ROOT_STATUS_REGISTER</a> structure that describes the PCIe root status register of the PCIe capability structure.


### -field DeviceCapabilities2




### -field DeviceControl2




### -field DeviceStatus2






## -remarks



The PCI_EXPRESS_CAPABILITY structure is available in Windows Server 2008 and later versions of Windows.

For additional information about the PCIe capability structure, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=69486">PCI Express Specification</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537463">PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537468">PCI_EXPRESS_LINK_CAPABILITIES_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537473">PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537477">PCI_EXPRESS_ROOT_STATUS_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537474">PCI_EXPRESS_ROOT_CONTROL_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537464">PCI_EXPRESS_DEVICE_CONTROL_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537465">PCI_EXPRESS_DEVICE_STATUS_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537459">PCI_EXPRESS_CAPABILITIES_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537454">PCI_CAPABILITIES_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537560">PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537470">PCI_EXPRESS_LINK_STATUS_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537562">PCI_EXPRESS_SLOT_CONTROL_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537469">PCI_EXPRESS_LINK_CONTROL_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537564">PCI_EXPRESS_SLOT_STATUS_REGISTER</a>



 

 


