---
UID: NS:miniport._PCI_SLOT_NUMBER
title: _PCI_SLOT_NUMBER (miniport.h)
description: The PCI_SLOT_NUMBER structure is obsolete.
old-location: kernel\pci_slot_number.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PCI_SLOT_NUMBER structure"]
ms.keywords: "*PPCI_SLOT_NUMBER, PCI_SLOT_NUMBER, PCI_SLOT_NUMBER structure [Kernel-Mode Driver Architecture], PPCI_SLOT_NUMBER, PPCI_SLOT_NUMBER structure pointer [Kernel-Mode Driver Architecture], _PCI_SLOT_NUMBER, kernel.pci_slot_number, kstruct_c_e9aa5e88-0c5d-4740-80f3-4b59da610598.xml, wdm/PCI_SLOT_NUMBER, wdm/PPCI_SLOT_NUMBER"
req.header: miniport.h
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
req.typenames: PCI_SLOT_NUMBER, *PPCI_SLOT_NUMBER
f1_keywords:
 - _PCI_SLOT_NUMBER
 - miniport/_PCI_SLOT_NUMBER
 - PPCI_SLOT_NUMBER
 - miniport/PPCI_SLOT_NUMBER
 - PCI_SLOT_NUMBER
 - miniport/PCI_SLOT_NUMBER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_SLOT_NUMBER
 - PPCI_SLOT_NUMBER
 - PCI_SLOT_NUMBER
---

# _PCI_SLOT_NUMBER structure (miniport.h)


## -description

The <b>PCI_SLOT_NUMBER</b> structure is <u>obsolete</u>. It defines the format of the <i>Slot</i> parameter to the obsolete <b>Hal<i>Xxx</i>BusData</b> routines when they are called with the <i>BusDataType</i> value <b>PCIConfiguration</b>.

## -struct-fields

### -field u

### -field u.bits

Specifies the particular device on a multifunction adapter at the given slot that is being configured. The <b>DeviceNumber</b> indicates the logical slot number for the adapter; the <b>FunctionNumber</b> indicates the particular device on that adapter.

### -field u.bits.DeviceNumber

### -field u.bits.FunctionNumber

### -field u.bits.Reserved

### -field u.AsULONG

Specifies the logical slot number of the device being configured.

## -remarks

Drivers of PCI devices can call <a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusData</a> or <a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusDataByOffset</a> more than once for the same slot number to get the configuration information for their device(s).

For example, a driver might search for devices it supports on all PCI buses in the machine first, and then call <code>HalGetBusData(ByOffset)</code> again to request more configuration information about devices of interest. Such a driver could code a loop that calls <code>HalGetBusData(ByOffset)</code> with an input <code>Buffer</code> of sufficient <code>Length</code> only to contain enough of the <a href="/previous-versions/windows/hardware/drivers/ff537455(v=vs.85)">PCI_COMMON_CONFIG</a> to determine the <code>VendorID</code> and <code>DeviceID</code> of each PCI device. After finding the <code>Slot</code> numbers for any promising PCI devices, the driver would call <a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusData</a> or <a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusDataByOffset</a> one or more times with additional buffer space to get the information needed to configure its devices.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalAssignSlotResources</a>



<a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusData</a>



<a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusDataByOffset</a>



<a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalSetBusData</a>



<a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalSetBusDataByOffset</a>



<a href="/previous-versions/windows/hardware/drivers/ff537455(v=vs.85)">PCI_COMMON_CONFIG</a>

