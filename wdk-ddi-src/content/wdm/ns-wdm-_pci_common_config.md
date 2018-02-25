---
UID: NS:wdm._PCI_COMMON_CONFIG
title: "_PCI_COMMON_CONFIG"
author: windows-driver-content
description: The PCI_COMMON_CONFIG structure is obsolete.
old-location: kernel\pci_common_config.htm
old-project: kernel
ms.assetid: 239d0c0a-e78e-40d5-b359-36910bdd9358
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PPCI_COMMON_CONFIG, ,, C, F, G, I, M, N, O, P, PCI_COMMON_CONFIG, PCI_COMMON_CONFIG structure [Kernel-Mode Driver Architecture], PPCI_COMMON_CONFIG, PPCI_COMMON_CONFIG structure pointer [Kernel-Mode Driver Architecture], _, _PCI_COMMON_CONFIG, kernel.pci_common_config, kstruct_c_42f21057-e812-4a4d-96c5-f1177a03982b.xml, wdm/PCI_COMMON_CONFIG, wdm/PPCI_COMMON_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	PCI_COMMON_CONFIG
product: Windows
targetos: Windows
req.typenames: PCI_COMMON_CONFIG, *PPCI_COMMON_CONFIG, PCI_COMMON_CONFIG, *PPCI_COMMON_CONFIG
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




### -field DeviceSpecific

Contains any device-specific initialization information that is available.


### -field PCI_COMMON_HEADER

 




#### - VendorID

Identifies the manufacturer of the device. This must be a value allocated by the PCI SIG.


#### - DeviceID

Identifies the particular device. This value is assigned by the manufacturer.


#### - Command

Accesses the PCI device's control register. Writing a zero to this register renders the device logically disconnected from the PCI bus except for configuration access. Otherwise, the functionality of the register is device-dependent. Possible system-defined bit encodings for this member include:

PCI_ENABLE_IO_SPACE

PCI_ENABLE_MEMORY_SPACE

PCI_ENABLE_BUS_MASTER

PCI_ENABLE_SPECIAL_CYCLES

PCI_ENABLE_WRITE_AND_VALIDATE

PCI_ENABLE_VGA_COMPATIBLE_PALETTE

PCI_ENABLE_PARITY

PCI_ENABLE_WAIT_CYCLE

PCI_ENABLE_SERR

PCI_ENABLE_FAST_BACK_TO_BACK


#### - Status

Accesses the PCI device's status register. The functionality of this register is device-dependent. Possible system-defined bit encodings for this member include:

PCI_STATUS_FAST_BACK_TO_BACK             // read-only

PCI_STATUS_DATA_PARITY_DETECTED

PCI_STATUS_DEVSEL                                      // 2 bits wide

PCI_STATUS_SIGNALED_TARGET_ABORT

PCI_STATUS_RECEIVED_TARGET_ABORT

PCI_STATUS_RECEIVED_MASTER_ABORT

PCI_STATUS_SIGNALED_SYSTEM_ERROR

PCI_STATUS_DETECTED_PARITY_ERROR


#### - RevisionID

Specifies the revision level of the device described by the <b>DeviceID</b> member. This value is assigned by the manufacturer. 


#### - ProgIf

Identifies the register-level programming interface, if any, for the device, according to the PCI classification scheme.


#### - SubClass

Identifies the subtype, if any, of the device, according to the PCI classification scheme.


#### - BaseClass

Identifies type of the device, according to the PCI classification scheme.


#### - CacheLineSize

Contains the system cache line size in 32-bit units. This member is relevant only for PCI bus-master devices. The system determines this value during the boot process.


#### - LatencyTimer

Contains the value of the latency timer in units of PCI bus clocks. This member is relevant only for PCI bus-master devices. The system determines this value during the boot process.


#### - HeaderType

The system ORs the value of this member with PCI_MULTIFUNCTION, if appropriate to the device. The value of this member indicates the PCI_HEADER_TYPE_0 layout that follows.


#### - BIST

Zero indicates that the device does not support built-in self-test. Otherwise, the device supports built-in self-test according to the PCI standard.


#### - u



#### type0

Drivers call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a> to configure these values and to get back the bus-relative values passed to other configuration routines.



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

Drivers call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a> to configure these values and to get back the bus-relative values passed to other configuration routines.



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


###### - u.type0.Reserved1

Reserved.


###### - u.type0.ROMBaseAddress

ROM base address.


###### - u.type0.Reserved2

Reserved.


###### - u.type0.InterruptLine

Interrupt line number.


###### - u.type0.InterruptPin

Interrupt pin number.


###### - u.type0.MinimumGrant

Minimum grant.


###### - u.type0.MaximumLatency

Maximum latency.


## -remarks



Certain members of this structure have read-only values, so attempts to reset them are ignored. These members include the following: <b>VendorID</b>, <b>DeviceID</b>, <b>RevisionID</b>, <b>ProgIf</b>, <b>SubClass</b>, <b>BaseClass</b>, <b>HeaderType</b>, <b>InterruptPin</b>, <b>MinimumGrant</b>, and <b>MaximumLatency.</b>

Other members are provisionally read-only: that is, the system initializes them to their correct values, so drivers can safely treat them as read-only. However, they can be reset if a bus-master driver finds it necessary. These members include the following: <b>CacheLineSize</b> and <b>LatencyTimer</b>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546628">HalSetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCI_COMMON_CONFIG structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

