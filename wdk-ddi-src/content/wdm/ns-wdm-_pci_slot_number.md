---
UID: NS:wdm._PCI_SLOT_NUMBER
title: "_PCI_SLOT_NUMBER"
author: windows-driver-content
description: The PCI_SLOT_NUMBER structure is obsolete.
old-location: kernel\pci_slot_number.htm
old-project: kernel
ms.assetid: 0e04813d-e138-435e-8357-562f79a3a4a2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PCI_SLOT_NUMBER structure [Kernel-Mode Driver Architecture], PPCI_SLOT_NUMBER, kstruct_c_e9aa5e88-0c5d-4740-80f3-4b59da610598.xml, _PCI_SLOT_NUMBER, PPCI_SLOT_NUMBER structure pointer [Kernel-Mode Driver Architecture], PCI_SLOT_NUMBER, wdm/PCI_SLOT_NUMBER, kernel.pci_slot_number, *PPCI_SLOT_NUMBER, wdm/PPCI_SLOT_NUMBER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PCI_SLOT_NUMBER
product: Windows
targetos: Windows
req.typenames: PCI_SLOT_NUMBER, *PPCI_SLOT_NUMBER
req.product: Windows 10 or later.
---

# _PCI_SLOT_NUMBER structure


## -description


The <b>PCI_SLOT_NUMBER</b> structure is <u>obsolete</u>. It defines the format of the <i>Slot</i> parameter to the obsolete <b>Hal<i>Xxx</i>BusData</b> routines when they are called with the <i>BusDataType</i> value <b>PCIConfiguration</b>.


## -syntax


````
typedef struct _PCI_SLOT_NUMBER {
  union {
    struct {
      ULONG DeviceNumber  :5;
      ULONG FunctionNumber  :3;
      ULONG Reserved  :24;
    } bits;
    ULONG AsULONG;
  } u;
} PCI_SLOT_NUMBER, *PPCI_SLOT_NUMBER;
````


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


Drivers of PCI devices can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a> more than once for the same slot number to get the configuration information for their device(s).

For example, a driver might search for devices it supports on all PCI buses in the machine first, and then call <code>HalGetBusData(ByOffset)</code> again to request more configuration information about devices of interest. Such a driver could code a loop that calls <code>HalGetBusData(ByOffset)</code> with an input <code>Buffer</code> of sufficient <code>Length</code> only to contain enough of the <a href="..\wdm\ns-wdm-_pci_common_config.md">PCI_COMMON_CONFIG</a> to determine the <code>VendorID</code> and <code>DeviceID</code> of each PCI device. After finding the <code>Slot</code> numbers for any promising PCI devices, the driver would call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a> one or more times with additional buffer space to get the information needed to configure its devices.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>

<a href="..\wdm\ns-wdm-_pci_common_config.md">PCI_COMMON_CONFIG</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546628">HalSetBusData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCI_SLOT_NUMBER structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

