---
UID: NS:wdm._PCI_COMMON_CONFIG
title: _PCI_COMMON_CONFIG (wdm.h)
description: The _PCI_COMMON_CONFIG structure (wdm.h) defines standard PCI configuration information.
old-location: kernel\pci_common_config.htm
tech.root: kernel
ms.date: 12/01/2021
keywords: ["PCI_COMMON_CONFIG structure"]
ms.keywords: "*PPCI_COMMON_CONFIG, PCI_COMMON_CONFIG, PCI_COMMON_CONFIG structure [Kernel-Mode Driver Architecture], PPCI_COMMON_CONFIG, PPCI_COMMON_CONFIG structure pointer [Kernel-Mode Driver Architecture], _PCI_COMMON_CONFIG, kernel.pci_common_config, kstruct_c_42f21057-e812-4a4d-96c5-f1177a03982b.xml, wdm/PCI_COMMON_CONFIG, wdm/PPCI_COMMON_CONFIG"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.irql: 
targetos: Windows
req.typenames: PCI_COMMON_CONFIG, *PPCI_COMMON_CONFIG
f1_keywords:
 - _PCI_COMMON_CONFIG
 - wdm/_PCI_COMMON_CONFIG
 - PPCI_COMMON_CONFIG
 - wdm/PPCI_COMMON_CONFIG
 - PCI_COMMON_CONFIG
 - wdm/PCI_COMMON_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _PCI_COMMON_CONFIG
 - PPCI_COMMON_CONFIG
 - PCI_COMMON_CONFIG
---

# _PCI_COMMON_CONFIG structure (wdm.h)

## -description

The **PCI_COMMON_CONFIG** structure defines standard PCI configuration information returned by the [HalGetBusData](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)) or [HalGetBusDataByOffset](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)) routine for the input *BusDataType* PCIConfiguration, assuming the caller-allocated *Buffer* is of sufficient *Length*.

## -struct-fields

### -field DeviceSpecific

Contains any device-specific initialization information that is available.


#### type0

Drivers call [HalAssignSlotResources](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)) to configure these values and to get back the bus-relative values passed to other configuration routines.

##### BaseAddresses

Base addresses.

##### Reserved1

Reserved.

##### ROMBaseAddress

ROM base address.

##### Reserved2

Reserved.

##### InterruptLine

Interrupt line number.

##### InterruptPin

Interrupt pin number.

##### MinimumGrant

Minimum grant.

##### MaximumLatency

Maximum latency.

##### - u.type0

Drivers call [HalAssignSlotResources](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)) to configure these values and to get back the bus-relative values passed to other configuration routines.

##### type0.BaseAddresses

Base addresses.

##### type0.Reserved1

Reserved.

##### type0.ROMBaseAddress

ROM base address.

##### type0.Reserved2

Reserved.

##### type0.InterruptLine

Interrupt line number.

##### type0.InterruptPin

Interrupt pin number.

##### type0.MinimumGrant

Minimum grant.

##### type0.MaximumLatency

Maximum latency.

###### - u.type0.BaseAddresses

Base addresses.

###### - u.type0.InterruptLine

Interrupt line number.

###### - u.type0.InterruptPin

Interrupt pin number.

###### - u.type0.MaximumLatency

Maximum latency.

###### - u.type0.MinimumGrant

Minimum grant.

###### - u.type0.ROMBaseAddress

ROM base address.

###### - u.type0.Reserved1

Reserved.

###### - u.type0.Reserved2

Reserved.

## -remarks

Certain members of this structure have read-only values, so attempts to reset them are ignored. These members include the following: **VendorID**, **DeviceID**, **RevisionID**, **ProgIf**, **SubClass**, **BaseClass**, **HeaderType**, **InterruptPin**, **MinimumGrant**, and **MaximumLatency.**

Other members are provisionally read-only: that is, the system initializes them to their correct values, so drivers can safely treat them as read-only. However, they can be reset if a bus-master driver finds it necessary. These members include the following: **CacheLineSize** and **LatencyTimer**.

## -see-also

[HalAssignSlotResources](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85))

[HalGetBusData](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85))

[HalGetBusDataByOffset](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85))

[HalSetBusData](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85))

[HalSetBusDataByOffset](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85))
