---
UID: NS:ntddk._PCI_EXPRESS_LINK_CONTROL_REGISTER
title: _PCI_EXPRESS_LINK_CONTROL_REGISTER (ntddk.h)
description: The PCI_EXPRESS_LINK_CONTROL_REGISTER structure describes a PCI Express (PCIe) link control register of a PCIe capability structure.
old-location: pci\pci_express_link_control_register.htm
tech.root: PCI
ms.assetid: f4f8bd0d-fad7-4712-92ca-44d45969142d
ms.date: 02/24/2018
ms.keywords: "*PPCI_EXPRESS_LINK_CONTROL_REGISTER, PCI.pci_express_link_control_register, PCI_EXPRESS_LINK_CONTROL_REGISTER, PCI_EXPRESS_LINK_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_LINK_CONTROL_REGISTER, PPCI_EXPRESS_LINK_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_LINK_CONTROL_REGISTER, ntddk/PCI_EXPRESS_LINK_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_LINK_CONTROL_REGISTER, pci_struct_0fc5be0f-aae8-4d59-a569-030eb593e927.xml"
ms.topic: struct
f1_keywords:
 - "ntddk/PCI_EXPRESS_LINK_CONTROL_REGISTER"
req.header: ntddk.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- PCI_EXPRESS_LINK_CONTROL_REGISTER
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_LINK_CONTROL_REGISTER, *PPCI_EXPRESS_LINK_CONTROL_REGISTER
---

# _PCI_EXPRESS_LINK_CONTROL_REGISTER structure


## -description


The PCI_EXPRESS_LINK_CONTROL_REGISTER structure describes a PCI Express (PCIe) link control register of a PCIe capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_LINK_CONTROL_REGISTER {
  struct {
    USHORT ActiveStatePMControl  :2;
    USHORT Rsvd1  :1;
    USHORT ReadCompletionBoundary  :1;
    USHORT LinkDisable  :1;
    USHORT RetrainLink  :1;
    USHORT CommonClockConfig  :1;
    USHORT ExtendedSynch  :1;
    USHORT EnableClockPowerManagement  :1;
    USHORT Rsvd2  :7;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_LINK_CONTROL_REGISTER, *PPCI_EXPRESS_LINK_CONTROL_REGISTER;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_LINK_CONTROL_REGISTER structure.


#### - ActiveStatePMControl

The level of active state power management that is enabled on the PCIe link. Possible values are:





#### L0sAndL1EntryDisabled

L0s and L1 are both disabled.



#### L0sEntryEnabled

L0s is enabled.



#### L1EntryEnabled

L1 is enabled.



#### L0sAndL1EntryEnabled

L0s and L1 are both enabled.


#### - CommonClockConfig

A single bit that indicates that this component and the component at the opposite end of the link are operating with a distributed common reference clock. If this bit is clear, this component and the component at the opposite end of the link are operating with an asynchronous reference clock.


#### - EnableClockPowerManagement

A single bit that indicates that clock power management is enabled.


#### - ExtendedSynch

A single bit that indicates that additional ordered sets are transmitted when exiting the L0s state and when in the recovery state.


#### - LinkDisable

A single bit that indicates that the link is disabled. This member is not applicable for endpoint devices, PCIe-to-PCI or PCI-X bridges, and upstream ports of switches.


#### - ReadCompletionBoundary

The read completion boundary (RCB) value for the root port or the root port upstream from the endpoint. If the bit is clear, the RCB is 64 byte. If the bit is set, the RCB is 128 byte. This member is not applicable for switch ports.


#### - RetrainLink

A single bit that is used to initiate retraining of the link. Reads of this bit always return zero. This member is not applicable for endpoint devices, PCIe-to-PCI or PCI-X bridges, and upstream ports of switches.


#### - Rsvd1

Reserved.


#### - Rsvd2

Reserved.


## -remarks



The PCI_EXPRESS_LINK_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_LINK_CONTROL_REGISTER structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a> structure.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a>



 

 


