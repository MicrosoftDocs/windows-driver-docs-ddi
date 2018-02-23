---
UID: NS:strmini._PORT_CONFIGURATION_INFORMATION
title: "_PORT_CONFIGURATION_INFORMATION"
author: windows-driver-content
description: PORT_CONFIGURATION_INFORMATION (SCSI) contains configuration information for an HBA.
old-location: storage\port_configuration_information__scsi_.htm
old-project: storage
ms.assetid: f3c9d851-d30d-4757-82a3-225ee67528c1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PPORT_CONFIGURATION_INFORMATION structure pointer [Storage Devices], *PPORT_CONFIGURATION_INFORMATION, srb/_PORT_CONFIGURATION_INFORMATION, structs-scsiport_1a472219-5839-443c-a3a1-26c9708b3b18.xml, srb/PPORT_CONFIGURATION_INFORMATION, PPORT_CONFIGURATION_INFORMATION, PORT_CONFIGURATION_INFORMATION, storage.port_configuration_information__scsi_, PORT_CONFIGURATION_INFORMATION structure [Storage Devices], _PORT_CONFIGURATION_INFORMATION structure [Storage Devices], _PORT_CONFIGURATION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: Srb.h, Storport.h, Strmini.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	srb.h
apiname:
-	PORT_CONFIGURATION_INFORMATION
product: Windows
targetos: Windows
req.typenames: PORT_CONFIGURATION_INFORMATION, *PPORT_CONFIGURATION_INFORMATION
req.product: Windows 10 or later.
---

# _PORT_CONFIGURATION_INFORMATION structure


## -description


PORT_CONFIGURATION_INFORMATION (SCSI) contains configuration information for an HBA. The OS-specific port driver allocates and initializes this structure, supplies as much HBA-specific configuration information as possible, and passes the structure to the miniport driver's <i>HwScsiFindAdapter</i> routine. The port driver gets some of the information for this structure from the miniport driver's HW_INITIALIZATION_DATA structure. The miniport driver's <i>HwScsiFindAdapter</i> routine is responsible for determining whether the miniport driver can support the HBA and, if so, for filling in the pertinent remaining information in the PORT_CONFIGURATION_INFORMATION structure.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _PORT_CONFIGURATION_INFORMATION {
  ULONG           Length;
  ULONG           SystemIoBusNumber;
  INTERFACE_TYPE  AdapterInterfaceType;
  ULONG           BusInterruptLevel;
  ULONG           BusInterruptVector;
  KINTERRUPT_MODE InterruptMode;
  ULONG           MaximumTransferLength;
  ULONG           NumberOfPhysicalBreaks;
  ULONG           DmaChannel;
  ULONG           DmaPort;
  DMA_WIDTH       DmaWidth;
  DMA_SPEED       DmaSpeed;
  ULONG           AlignmentMask;
  ULONG           NumberOfAccessRanges;
  ACCESS_RANGE    (*AccessRanges)[];
  PVOID           Reserved;
  UCHAR           NumberOfBuses;
  UCHAR           InitiatorBusId[8];
  BOOLEAN         ScatterGather;
  BOOLEAN         Master;
  BOOLEAN         CachesData;
  BOOLEAN         AdapterScansDown;
  BOOLEAN         AtdiskPrimaryClaimed;
  BOOLEAN         AtdiskSecondaryClaimed;
  BOOLEAN         Dma32BitAddresses;
  BOOLEAN         DemandMode;
  BOOLEAN         MapBuffers;
  BOOLEAN         NeedPhysicalAddresses;
  BOOLEAN         TaggedQueuing;
  BOOLEAN         AutoRequestSense;
  BOOLEAN         MultipleRequestPerLu;
  BOOLEAN         ReceiveEvent;
  BOOLEAN         RealModeInitialized;
  BOOLEAN         BufferAccessScsiPortControlled;
  UCHAR           MaximumNumberOfTargets;
  UCHAR           ReservedUchars[2];
  ULONG           SlotNumber;
  ULONG           BusInterruptLevel2;
  ULONG           BusInterruptVector2;
  KINTERRUPT_MODE InterruptMode2;
  ULONG           DmaChannel2;
  ULONG           DmaPort2;
  DMA_WIDTH       DmaWidth2;
  DMA_SPEED       DmaSpeed2;
  ULONG           DeviceExtensionSize;
  ULONG           SpecificLuExtensionSize;
  ULONG           SrbExtensionSize;
  UCHAR           Dma64BitAddresses;
  BOOLEAN         ResetTargetSupported;
  UCHAR           MaximumNumberOfLogicalUnits;
  BOOLEAN         WmiDataProvider;
} PORT_CONFIGURATION_INFORMATION, *PPORT_CONFIGURATION_INFORMATION;
````


## -struct-fields




### -field SizeOfThisPacket

 


### -field HwDeviceExtension

 


### -field ClassDeviceObject

 


### -field PhysicalDeviceObject

 


### -field SystemIoBusNumber

Specifies the system-assigned number of the I/O bus to which the HBA is connected. The OS-specific port driver always initializes this member. Its value is system-assigned because the platform might have several I/O buses of the given <b>AdapterInterfaceType</b>.


### -field AdapterInterfaceType

Identifies the I/O bus interface. The OS-specific port driver always sets this member to the value specified by the miniport driver in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a> structure.


### -field BusInterruptLevel

Specifies the bus-relative interrupt request level. The OS-specific port driver makes no assumptions about the HBA's interrupt usage, so the default value is zero. Depending on the given <b>AdapterInterfaceType</b> and HBA, the value set for this member can correspond to the IRQL for the bus, such as for <b>Isa</b> and <b>MicroChannel</b> type buses. Drivers of <b>Eisa</b> HBAs must set this value to the bus-relative IRQL for the HBA if the adapter is configured for level-sensitive interrupts.


### -field BusInterruptVector

Specifies the bus-relative vector returned by the HBA. The OS-specific port driver makes no assumptions about the HBA's interrupt usage, so the default value is zero. This member is irrelevant to drivers that set up the <b>BusInterruptLevel</b> member for their HBAs. It is pertinent for HBAs on types of I/O buses that use interrupt vectors, such as <b>PCIBus</b>.


### -field InterruptMode

Specifies whether the HBA uses <b>LevelSensitive</b> or <b>Latched</b> (sometimes called "edge-triggered") interrupts. The OS-specific port driver initializes this member to an appropriate value for the bus and the device--for example, <b>LevelSensitive</b> for <b>PCIBus</b>. Drivers of <b>Eisa</b> HBAs must reset this value if the adapter is configured for level-sensitive interrupts, as must drivers of HBAs on I/O buses that use level-sensitive interrupts, such as <b>MicroChannel</b> type buses.


### -field DmaChannel

Specifies the DMA channel used by a subordinate HBA. By default, the value of this member is SP_UNINITIALIZED_VALUE. If the HBA uses a system DMA controller and the given <b>AdapterInterfaceType</b> is any value except <b>MicroChannel</b>, the miniport driver must reset this member.


### -field NumberOfAccessRanges

Specifies the number of <b>AccessRanges</b> elements in the array, described next. The OS-specific port driver always sets this member to the value passed in the HW_INITIALIZATION_DATA structure when the miniport driver called <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>.


### -field AccessRanges

 


### -field StreamDescriptorSize

 


### -field Irp

 


### -field InterruptObject

 


### -field DmaAdapterObject

 


### -field RealPhysicalDeviceObject

 


### -field Reserved

Reserved for system use and not available for use by miniport drivers.


#### - Length

Specifies the size of this structure in bytes, as returned by <b>sizeof</b>(). In effect, this member, which is always initialized by the OS-specific port driver, indicates the version of this structure used by the port driver.


#### - MaximumTransferLength

Specifies the maximum number of bytes the HBA can transfer in a single transfer operation. By default, the value of this member is SP_UNINITIALIZED_VALUE, which indicates an unlimited maximum transfer size. If its HBA has more limited transfer support, a miniport driver must reset this member according to the HBA's transfer capacity. If a miniport driver's HwScsiInterrupt routine cannot disable interrupts on the HBA, this member can be adjusted during driver development to ensure that time spent in that miniport driver's ISR does not cause the mouse to "jump" or serial/parallel throughput to drop to a user-noticeable level.


#### - NumberOfPhysicalBreaks

Specifies the maximum number of breaks between address ranges that a data buffer can have if the HBA supports scatter/gather. In other words, the number of scatter/gather lists minus one. By default, the value of this member is SP_UNINITIALIZED_VALUE, which indicates the HBA can support an unlimited number of physical discontiguities. If the port driver sets a value for this member, the miniport driver can adjust the value lower but no higher. If this member is SP_UNINITIALIZED_VALUE, the miniport driver must reset this member according to the HBA's scatter/gather capacity, with zero representing no scatter/gather support.


#### - DmaPort

Specifies the DMA port used by a subordinate HBA. By default, the value of this member is SP_UNINITIALIZED_VALUE. If the HBA uses a system DMA controller and the given <b>AdapterInterfaceType</b> is <b>MicroChannel</b>, the miniport driver must set this member.


#### - DmaWidth

Specifies the width of DMA transfers if the HBA uses DMA. By default, the value of this member is zero. If its HBA does DMA, the miniport driver must reset this member to one of the following: <b>Width8Bits</b>, <b>Width16Bits</b>, or <b>Width32Bits</b>.


#### - DmaSpeed

Specifies the DMA data-transfer speed for <b>Eisa</b> HBAs. By default, the value of this member specifies compatibility timing. Acceptable values for this member are any of the following: <b>Compatible</b>, <b>TypeA</b>, <b>TypeB</b>, or <b>TypeC</b>.


#### - AlignmentMask

Contains a mask indicating the alignment restrictions for buffers required by the HBA for transfer operations. Valid mask values are also restricted by characteristics of the memory managers on different versions of Windows. The mask values that are permitted under Windows 95 or Windows 98 are 0 (byte aligned), 1 (word aligned) or 3 (DWORD aligned). Under Windows NT and Windows 2000 the valid mask values are 0 (byte aligned), 1 (word aligned), 3 (DWORD aligned) and 7 (double DWORD aligned). The miniport driver should set this mask if the HBA supports scatter/gather. 


#### - (*AccessRanges)

Pointer to an array of <a href="..\strmini\ns-strmini-_access_range.md">ACCESS_RANGE</a>-type elements. The given <b>NumberOfAccessRanges</b> determines how many elements must be configured with bus-relative range values. The <b>AccessRanges</b> pointer must be <b>NULL</b> if <b>NumberOfAccessRanges</b> is zero. If possible, the OS-specific port driver initializes this member's elements, possibly from the registry or possibly by interrogating an I/O bus, for an HBA it found by using the miniport driver's specified <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a>. Otherwise, the port driver initializes all values within array elements to zero.

If any access range element is set to nonzero values on entry to the miniport driver's <a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a> routine, the miniport driver <i>must</i> map the supplied addresses with <a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a> and use the corresponding logical addresses to verify whether that HBA is one it supports. If the input <b>AccessRanges</b> have nonzero values supplied, a miniport driver <i>should neverattempt</i> to scan the I/O bus for HBAs it supports using a set of driver-devised port/memory addresses that its HBA(s) might use.


#### - NumberOfBuses

Specifies the number of SCSI buses controlled by the HBA. By default, the value of this member is zero.


#### - InitiatorBusId

Indicates the initiator bus ID. If the input <b>InitiatorBusId</b>[0] has the value zero, the miniport driver can assign a default value if its HBA does not require the use of particular value(s) determined by querying the HBA. Otherwise, the miniport driver should use any nonzero value assigned by the port driver if possible. Every miniport driver must update <b>InitiatorBusId</b> specifications to match what its HBA uses, if necessary querying the HBA to determine the appropriate values(s).

A miniport driver must set an entry for each SCSI bus supported by the HBA, as indicated by the value of <b>NumberOfBuses</b>.


#### - ScatterGather

Indicates when <b>TRUE</b> that the HBA supports scatter/gather. When <b>FALSE</b> the HBA does not support scatter/gather. By default, the value of this member is <b>FALSE</b>.


#### - Master

Indicates when <b>TRUE</b> that the HBA is a bus master. When <b>FALSE</b>, the HBA is not a bus master. By default, the value of this member is <b>FALSE</b>.


#### - CachesData

Indicates when <b>TRUE</b> that the HBA caches data or maintains cached state on the peripherals. When <b>FALSE</b> the HBA does not cache data or maintain cached state on the peripherals. By default, the value of this member is <b>FALSE</b>. If this is reset to <b>TRUE</b>, the OS-specific port driver notifies the miniport driver when certain system events occur, such as file system cache flushes and system shutdown. For example, if a controller on the bus mirrors two disks, the miniport driver would normally set this member to <b>TRUE</b>.


#### - AdapterScansDown

Indicates when <b>TRUE</b> that the BIOS for the HBA scans for SCSI bus targets from seven to zero. When <b>FALSE</b>, the BIOS for the HBA looks for SCSI bus targets, starting with an ID zero and scanning upwards to (but not including) <b>MaximumTargetIds</b>. By default, the value of <b>AdapterScansDown</b> is <b>FALSE</b>.


#### - AtdiskPrimaryClaimed

Indicates when <b>TRUE</b> that the primary "AT" (WD1003-compatible) disk address range, 0x1F0 to 0x1FF, has been claimed in the registry by another driver for its device. The OS-specific port driver always initializes this member. If the input value of this member is <b>TRUE</b>, a miniport driver should assume that an already loaded driver has claimed the device range. If the input value is <b>FALSE</b>, a miniport driver can claim the address range for an HBA that emulates an "AT" disk controller and reset this member to <b>TRUE</b>, thereby preventing access to this range by the "AT" disk driver or subsequently loaded miniport drivers.


#### - AtdiskSecondaryClaimed

Indicates when <b>TRUE</b> that the secondary AT disk address range, 0x170 to 0x17F has been claimed in the registry by another driver for its device. When <b>FALSE</b> the secondary AT disk address range has not been claimed in the registry by another driver. The OS-specific port driver always initializes this member. Miniport drivers should treat this member as for <b>AtdiskPrimaryClaimed</b>.


#### - Dma32BitAddresses

Indicates when <b>TRUE</b> that the HBA has 32 address lines and can access memory with physical addresses greater than 0x00FFFFFF. When <b>FALSE</b> the HBA has either a number of DMA address lines other than 32. By default, the value of this member is <b>FALSE</b>. If the miniport driver sets <b>Dma64BitAddresses</b>, this member must be <b>FALSE</b>.


#### - DemandMode

Indicates when <b>TRUE</b> that the system DMA controller should be programmed for demand-mode rather than single-cycle operations. If the HBA is not a subordinate device, this member should be <b>FALSE</b>.


#### - MapBuffers

Indicates when <b>TRUE</b> that data buffers must be mapped to system virtual address ranges. When <b>FALSE</b> the data buffers do not have to be mapped to system virtual addresses. The OS-specific port driver always sets this member to the value passed in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a> structure when the miniport driver called <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. A miniport driver can reset this value for any particular HBA it controls. If <b>FALSE</b>, the miniport driver must not access <b>Srb.DataBuffer</b> directly.


#### - NeedPhysicalAddresses

Indicates when <b>TRUE</b> that the miniport driver must translate virtual addresses to physical addresses, as required by the HBA. When <b>FALSE</b>, the miniport driver does not have to translate virtual addresses to physical addresses. The OS-specific port driver always sets this member to the value passed in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a> structure when the miniport driver called <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. A miniport driver can reset this value for any particular HBA it controls.


#### - TaggedQueuing

Indicates when <b>TRUE</b> that the HBA supports queuing of multiple requests with SCSI tags. When <b>FALSE</b>, the HBA does not support SCSI-tagged queuing. The OS-specific port driver always sets this member to the value passed in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a> structure when the miniport driver called <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. A miniport driver can reset this value for any particular HBA it controls.


#### - AutoRequestSense

Indicates when <b>TRUE</b> that the HBA supports auto request sense. When <b>FALSE</b> the HBA does not support auto request sense. The OS-specific port driver always sets this member to the value passed in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a> structure when the miniport driver called <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. A miniport driver can reset this value for any particular HBA it controls. This member must be set to <b>TRUE</b> before the driver of a bus-master HBA calls <a href="..\srb\nf-srb-scsiportgetuncachedextension.md">ScsiPortGetUncachedExtension</a>.


#### - MultipleRequestPerLu

Indicates when <b>TRUE</b> that the HBA supports multiple requests per logical unit. When <b>FALSE</b> the HBA does not support multiple requests per logical unit. The mechanism by which the adapter caches the requests is adapter-defined. The OS-specific port driver always sets this member to the value passed in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a> structure when the miniport driver called <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. A miniport driver can reset this value for any particular HBA it controls.


#### - ReceiveEvent

Indicates when <b>TRUE</b> that the HBA supports SCSI receive-event operations. When <b>FALSE</b> the HBA does not support SCSI receive-event operations. The OS-specific port driver always sets this member to the value passed in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a> structure when the miniport driver called <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. A miniport driver can reset this value for any particular HBA it controls.


#### - RealModeInitialized

Indicates when <b>TRUE</b> that an (x86-only) real-mode driver has already initialized the HBA. When <b>FALSE</b> the HBA has not been previously initialized by a real-mode driver. The OS-dependent port driver always initializes this member. If this is set to <b>TRUE</b>, the miniport driver must not initialize its HBA if the driver's initialization sequence is identical to real-mode HBA initialization; not reinitializing the HBA in these circumstances makes the miniport driver load much faster. The value of this member is irrelevant to any miniport driver that always initializes its HBA while running in protected mode on x86-based platforms and to all miniport drivers for which it is immaterial whether they are running on a CISC- or RISC-based platform.


#### - BufferAccessScsiPortControlled

Indicates when <b>TRUE</b> that the miniport driver always calls <b>ScsiPort</b><i>Xxx</i> to access data buffers and/or request-sense information in SRBs, thereby allowing the OS-specific port driver to optimize I/O request processing. When <b>FALSE</b> the miniport driver does not have to call <b>ScsiPort</b><i>Xxx</i> routines to access data buffers or request-sense information. Setting this member to <b>FALSE</b> can degrade the I/O performance of the HBA. Calling routines other than the <b>ScsiPort</b><i>Xxx</i> makes a miniport driver nonportable across Microsoft operating systems.


#### - MaximumNumberOfTargets

Specifies the number of target peripherals the HBA can control. By default, the value of this member is SCSI_MAXIMUM_TARGETS, according to the SCSI standard. A miniport driver can reset this member to a lesser value if the HBA has more limited capabilities or to a greater value, indicating that the HBA has wide-SCSI or Fibre Channel capabilities. This value is limited to SCSI_MAXIMUM_TARGETS_PER_BUS.


#### - ReservedUchars

Reserved for system use and not available for use by miniport drivers.


#### - SlotNumber

Specifies the slot number of an HBA with matching values to the <b>VendorId</b> and <b>DeviceId</b> that were specified in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a> structure when the miniport driver called <b>ScsiPortInitialize</b>.


#### - BusInterruptLevel2

Reserved for system use and not available for use by miniport drivers.


#### - BusInterruptVector2

Reserved for system use and not available for use by miniport drivers.


#### - InterruptMode2

Reserved for system use and not available for use by miniport drivers.


#### - DmaChannel2

Reserved for system use and not available for use by miniport drivers.


#### - DmaPort2

Reserved for system use and not available for use by miniport drivers.


#### - DmaWidth2

Reserved for system use and not available for use by miniport drivers.


#### - DmaSpeed2

Reserved for system use and not available for use by miniport drivers.


#### - DeviceExtensionSize

Specifies the size in bytes required by a miniport driver for its per-HBA device extension to handle data transfers larger than 64K, which might require larger scatter/gather lists than the size defined in the registry for this driver. 


#### - SpecificLuExtensionSize

Specifies the size in bytes required by the miniport driver for its per-logical-unit-storage, if any, to handle data transfers larger than 64K. Leave this member set to zero if the miniport driver does not maintain per-LU information for which it requires storage. This value is based on the assumption that the HBA is able to receive 32-bit addresses, regardless of what the controller can actually support. If additional space is needed in the LUN or SRB extensions to handle 64-bit addresses, then appropriate adjustments must be made to this value before using it with routines such as <a href="..\srb\nf-srb-scsiportgetuncachedextension.md">ScsiPortGetUncachedExtension</a>.


#### - SrbExtensionSize

Specifies the size in bytes required by the miniport driver for its per-request storage, if any, to handle data transfers larger than 64K. Set this member before calling <a href="..\srb\nf-srb-scsiportgetuncachedextension.md">ScsiPortGetUncachedExtension</a> to change the size of per-request storage based on <b>NumberOfPhysicalBreaks</b>. Leave this member set to zero if the miniport driver does not maintain per-SRB information for which it requires storage. This value is based on the assumption that the HBA is able to receive 32-bit addresses, regardless of what the controller can actually support. If additional space is needed in the LUN or SRB extensions to handle 64-bit addresses, then appropriate adjustments must be made to this value before using it with routines such as <b>ScsiPortGetUncachedExtension</b>.


#### - Dma64BitAddresses

Indicates that the HBA is able to access addresses greater than 4 GB, or 0x0FFFFFFFF if <b>Dma64BitAddresses</b> contains a value of SCSI_DMA64_MINIPORT_SUPPORTED. Prior to Windows 2000 the ScsiPort set this value based on the contents of <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a>. This is no longer the case. In Windows 2000 the value of <b>Dma64BitAddresses</b> is determined by the miniport driver callback <a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a> alone. If the operating system supports a 64-bit address space, the port driver passes a value of SCSI_DMA64_SYSTEM_SUPPORTED to the miniport driver in this member. If the HBA described by PORT_CONFIGURATION_INFORMATION also supports address spaces greater than 32-bits then the port/miniport driver is required to support full 64-bit addressing, and the miniport driver's callback <i>HwScsiFindAdapter</i> indicates this by assigning a value of SCSI_DMA64_MINIPORT_SUPPORTED to <b>Dma64BitAddresses</b>, writing over any previous value assigned by the port driver. The correct value must be assigned to the <b>Dma64BitAddresses</b> member before the miniport driver calls <a href="..\srb\nf-srb-scsiportgetuncachedextension.md">ScsiPortGetUncachedExtension</a>. 


#### - ResetTargetSupported

Obsolete. ScsiPort driver no longer sends SRB_FUNCTION_RESET_DEVICE requests to its miniport drivers. Do not use this member.


#### - MaximumNumberOfLogicalUnits

Specifies the maximum number of logical units per target the HBA can control. By default, the value of this member is SCSI_MAXIMUM_LOGICAL_UNITS. A miniport driver can reset this member to a lesser value if the HBA has more limited capabilities or to a greater value, indicating that the HBA has SCSI-3 capabilities. 


#### - WmiDataProvider

Indicates when <b>TRUE</b> that the miniport driver responds to Windows Management Instrumentation (WMI) requests. When <b>FALSE</b> the miniport driver does not respond to Windows Management Instrumentation (WMI) requests. By default, the value of this member is <b>FALSE</b>.


## -remarks



The specific members initialized depend on the HBA miniport driver and on the configuration information available to the OS-specific port driver. The OS-specific port driver sets default values in all members for which it cannot supply configuration information to the miniport driver's <i>HwScsiFindAdapter</i> routine.

All HBA miniport drivers should have at least one set of defaults to use for relevant members if the OS-specific port driver does not pass in all initialized values. 

The <i>HwScsiFindAdapter</i> routine must update all members relevant to an HBA that the driver supports.

Windows NT storage class drivers, which load later than miniport drivers, depend on the information supplied by each miniport driver's <i>HwScsiFindAdapter</i> routine to set up their subsequent I/O requests. For example, the <b>MaximumTransferLength </b>and <b>NumberOfPhysicalBreaks</b> values supplied by each miniport driver control whether a class driver must split large transfer requests into a set of partial transfers to suit the limits of the HBA.

Prior to Windows 2000, both the PORT_CONFIGURATION_INFORMATION and the HW_INITIALIZATION_DATA structures had a member called <b>Dma64BitAddresses</b>. In Windows 2000, <b>Dma64BitAddresses</b> has been eliminated from the HW_INITIALIZATION_DATA structure, and its definition has changed somewhat in PORT_CONFIGURATION_INFORMATION. The port driver no longer consults HW_INITIALIZATION_DATA in order to initialize <b>Dma64BitAddresses</b> in PORT_CONFIGURATION_INFORMATION.

The <b>Dma64BitAddresses</b> member of PORT_CONFIGURATION_INFORMATION should no longer be thought of as a BOOLEAN value. A value of SCSI_DMA64_SYSTEM_SUPPORTED indicates that the port/miniport driver is required to support 64-bit addressing, but the <b>ScsiPortGetUncachedExtension</b> routine still interprets any nonzero value of <b>Dma64BitAddresses</b> as indicating that 64-bit support is required. This means that <b>ScsiPortGetUncachedExtension</b> still functions properly when called by a legacy driver that assigns BOOLEAN values to <b>Dma64BitAddresses</b>.  

In addition to <b>Dma64BitAddresses</b>, both PORT_CONFIGURATION_INFORMATION and HW_INITIALIZATION_DATA have a pair of members called <b>SpecificLuExtensionSize</b> and <b>SrbExtensionSize</b> whose values must now be handled differently. The miniport driver must calculate the initial values of <b>SpecificLuExtensionSize</b> and <b>SrbExtensionSize</b> in HW_INITIALIZATION_DATA based on the assumption that the HBA is capable of receiving 32-bit addresses, regardless of what the controller can actually support. The default values for <b>SpecificLuExtensionSize</b> and <b>SrbExtensionSize </b>in PORT_CONFIGURATION_INFORMATION will also be based on an assumption of 32-bit addressing, since the values in PORT_CONFIGURATION_INFORMATION are derived from the values in HW_INITIALIZATION_DATA.

This means that if the miniport driver needs additional space in either the LUN extension or the SRB extension in order to handle 64 bit physical addresses, it must modify the values for <b>SpecificLuExtensionSize</b> and <b>SrbExtensionSize</b> in PORT_CONFIGURATION_INFORMATION to account for this before passing PORT_CONFIGURATION_INFORMATION to <b>ScsiPortGetUncachedExtension</b>.




## -see-also

<a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a>



<a href="..\srb\nf-srb-scsiportgetuncachedextension.md">ScsiPortGetUncachedExtension</a>



<a href="..\srb\nf-srb-scsiportvalidaterange.md">ScsiPortValidateRange</a>



<a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a>



<a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>



<a href="..\strmini\ns-strmini-_access_range.md">ACCESS_RANGE</a>



<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552654">DriverEntry of SCSI Miniport Driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20_PORT_CONFIGURATION_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

