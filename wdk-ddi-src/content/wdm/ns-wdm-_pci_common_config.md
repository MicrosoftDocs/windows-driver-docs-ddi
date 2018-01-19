---
UID: NS:wdm._PCI_COMMON_CONFIG
title: _PCI_COMMON_CONFIG
author: windows-driver-content
description: The PCI_COMMON_CONFIG structure is obsolete.
old-location: kernel\pci_common_config.htm
old-project: kernel
ms.assetid: 239d0c0a-e78e-40d5-b359-36910bdd9358
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PCI_COMMON_CONFIG, PCI_COMMON_CONFIG, *PPCI_COMMON_CONFIG
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
req.alt-api: PCI_COMMON_CONFIG
req.alt-loc: Wdm.h
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
req.typenames: PCI_COMMON_CONFIG, *PPCI_COMMON_CONFIG
req.product: Windows 10 or later.
---

# _PCI_COMMON_CONFIG structure



## -description
The <b>PCI_COMMON_CONFIG</b> structure is <u>obsolete</u>. It defines standard PCI configuration information returned by the obsolete <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a> routine for the input <i>BusDataType</i> PCIConfiguration, assuming the caller-allocated <i>Buffer</i> is of sufficient <i>Length</i>.



## -syntax

````
typedef struct _PCI_COMMON_CONFIG {
  USHORT VendorID;
  USHORT DeviceID;
  USHORT Command;
  USHORT Status;
  UCHAR  RevisionID;
  UCHAR  ProgIf;
  UCHAR  SubClass;
  UCHAR  BaseClass;
  UCHAR  CacheLineSize;
  UCHAR  LatencyTimer;
  UCHAR  HeaderType;
  UCHAR  BIST;
  union {
    struct {
      ULONG BaseAddresses[PCI_TYPE0_ADDRESSES];
      ULONG Reserved1[2];
      ULONG ROMBaseAddress;
      ULONG Reserved2[2];
      UCHAR InterruptLine;
      UCHAR InterruptPin;
      UCHAR MinimumGrant;
      UCHAR MaximumLatency;
    } type0;
  } u;
  UCHAR  DeviceSpecific[192];
} PCI_COMMON_CONFIG, *PPCI_COMMON_CONFIG;
````


## -struct-fields

### -field VendorID

Identifies the manufacturer of the device. This must be a value allocated by the PCI SIG.


### -field DeviceID

Identifies the particular device. This value is assigned by the manufacturer.


### -field Command

Accesses the PCI device's control register. Writing a zero to this register renders the device logically disconnected from the PCI bus except for configuration access. Otherwise, the functionality of the register is device-dependent. Possible system-defined bit encodings for this member include:

<dl>
<dd>
PCI_ENABLE_IO_SPACE

</dd>
<dd>
PCI_ENABLE_MEMORY_SPACE

</dd>
<dd>
PCI_ENABLE_BUS_MASTER

</dd>
<dd>
PCI_ENABLE_SPECIAL_CYCLES

</dd>
<dd>
PCI_ENABLE_WRITE_AND_VALIDATE

</dd>
<dd>
PCI_ENABLE_VGA_COMPATIBLE_PALETTE

</dd>
<dd>
PCI_ENABLE_PARITY

</dd>
<dd>
PCI_ENABLE_WAIT_CYCLE

</dd>
<dd>
PCI_ENABLE_SERR

</dd>
<dd>
PCI_ENABLE_FAST_BACK_TO_BACK

</dd>
</dl>

### -field Status

Accesses the PCI device's status register. The functionality of this register is device-dependent. Possible system-defined bit encodings for this member include:

<dl>
<dd>
PCI_STATUS_FAST_BACK_TO_BACK             // read-only

</dd>
<dd>
PCI_STATUS_DATA_PARITY_DETECTED

</dd>
<dd>
PCI_STATUS_DEVSEL                                      // 2 bits wide

</dd>
<dd>
PCI_STATUS_SIGNALED_TARGET_ABORT

</dd>
<dd>
PCI_STATUS_RECEIVED_TARGET_ABORT

</dd>
<dd>
PCI_STATUS_RECEIVED_MASTER_ABORT

</dd>
<dd>
PCI_STATUS_SIGNALED_SYSTEM_ERROR

</dd>
<dd>
PCI_STATUS_DETECTED_PARITY_ERROR

</dd>
</dl>

### -field RevisionID

Specifies the revision level of the device described by the <b>DeviceID</b> member. This value is assigned by the manufacturer. 


### -field ProgIf

Identifies the register-level programming interface, if any, for the device, according to the PCI classification scheme.


### -field SubClass

Identifies the subtype, if any, of the device, according to the PCI classification scheme.


### -field BaseClass

Identifies type of the device, according to the PCI classification scheme.


### -field CacheLineSize

Contains the system cache line size in 32-bit units. This member is relevant only for PCI bus-master devices. The system determines this value during the boot process.


### -field LatencyTimer

Contains the value of the latency timer in units of PCI bus clocks. This member is relevant only for PCI bus-master devices. The system determines this value during the boot process.


### -field HeaderType

The system ORs the value of this member with PCI_MULTIFUNCTION, if appropriate to the device. The value of this member indicates the PCI_HEADER_TYPE_0 layout that follows.


### -field BIST

Zero indicates that the device does not support built-in self-test. Otherwise, the device supports built-in self-test according to the PCI standard.


### -field u


### -field type0

Drivers call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a> to configure these values and to get back the bus-relative values passed to other configuration routines.


### -field BaseAddresses

Base addresses.


### -field Reserved1

Reserved.


### -field ROMBaseAddress

ROM base address.


### -field Reserved2

Reserved.


### -field InterruptLine

Interrupt line number.


### -field InterruptPin

Interrupt pin number.


### -field MinimumGrant

Minimum grant.


### -field MaximumLatency

Maximum latency.

</dd>
</dl>
</dd>
</dl>

### -field DeviceSpecific

Contains any device-specific initialization information that is available.


## -remarks
Certain members of this structure have read-only values, so attempts to reset them are ignored. These members include the following: <b>VendorID</b>, <b>DeviceID</b>, <b>RevisionID</b>, <b>ProgIf</b>, <b>SubClass</b>, <b>BaseClass</b>, <b>HeaderType</b>, <b>InterruptPin</b>, <b>MinimumGrant</b>, and <b>MaximumLatency.</b>

Other members are provisionally read-only: that is, the system initializes them to their correct values, so drivers can safely treat them as read-only. However, they can be reset if a bus-master driver finds it necessary. These members include the following: <b>CacheLineSize</b> and <b>LatencyTimer</b>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546628">HalSetBusData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCI_COMMON_CONFIG structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

