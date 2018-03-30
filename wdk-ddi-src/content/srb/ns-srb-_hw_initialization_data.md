---
UID: NS:srb._HW_INITIALIZATION_DATA
title: "_HW_INITIALIZATION_DATA"
author: windows-driver-content
description: Each SCSI miniport driver's DriverEntry routine must initialize with zeros and, then, fill in the relevant HW_INITIALIZATION_DATA (SCSI) information for the OS-specific port driver.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\hw_initialization_data__scsi_.htm
old-project: storage
ms.assetid: 58c80d37-a40d-4839-b516-a78720860cbc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PHW_INITIALIZATION_DATA, HW_INITIALIZATION_DATA, HW_INITIALIZATION_DATA structure [Storage Devices], PHW_INITIALIZATION_DATA, PHW_INITIALIZATION_DATA structure pointer [Storage Devices], _HW_INITIALIZATION_DATA, _HW_INITIALIZATION_DATA structure [Storage Devices], srb/HW_INITIALIZATION_DATA, srb/PHW_INITIALIZATION_DATA, storage.hw_initialization_data__scsi_, structs-scsiport_4d9f09a8-742b-4c72-8fc5-dd968bd990d6.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: srb.h
req.include-header: Srb.h, Strmini.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	srb.h
api_name:
-	HW_INITIALIZATION_DATA
product: Windows
targetos: Windows
req.typenames: HW_INITIALIZATION_DATA, *PHW_INITIALIZATION_DATA
req.product: Windows 10 or later.
---

# _HW_INITIALIZATION_DATA structure


## -description


Each SCSI miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine must initialize with zeros and, then, fill in the relevant HW_INITIALIZATION_DATA (SCSI) information for the OS-specific port driver.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field HwInitializationDataSize

Specifies the size of this structure in bytes, as returned by <b>sizeof</b>(). In effect, this member indicates the version of this structure being used by the miniport driver. A miniport driver's <b>DriverEntry</b> routine should set this member's value for the port driver.


### -field AdapterInterfaceType

Specifies the type of I/O bus to which the HBA is connected, which can be one of the following: <b>Internal</b>, <b>Isa</b>, <b>Eisa</b>, <b>MicroChannel</b>, <b>TurboChannel</b>, or <b>PCIBus</b>. However, additional types of buses will be supported in future. The upper bound on the types of buses supported is always <b>MaximumInterfaceType</b>.

If this is set to <b>PCIBus</b>, the miniport driver must supply values for the <b>VendorIdLength</b>, <b>VendorId</b>, <b>DeviceIdLength</b>, and <b>DeviceId</b> members, described later.


### -field HwInitialize

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557302">HwScsiInitialize</a> routine, which is a required entry point for all miniport drivers. The prototype for this routine is <a href="https://msdn.microsoft.com/library/windows/hardware/ff563866">PHW_INITIALIZE</a>. 


### -field HwStartIo

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557323">HwScsiStartIo</a> routine, which is a required entry point for all miniport drivers. The prototype for this routine is <a href="https://msdn.microsoft.com/library/windows/hardware/ff563876">PHW_STARTIO</a>.


### -field HwInterrupt

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557312">HwScsiInterrupt</a> routine, which is a required entry point for any miniport driver of an HBA that generates interrupts. Set this to <b>NULL</b> if the miniport driver needs no ISR. The prototype for this routine is <a href="https://msdn.microsoft.com/library/windows/hardware/ff563871">PHW_INTERRUPT</a>.


### -field HwFindAdapter

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine, which is a required entry point for all miniport drivers. The prototype for this routine is <a href="https://msdn.microsoft.com/library/windows/hardware/ff563862">PHW_FIND_ADAPTER</a>.


### -field HwResetBus

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557318">HwScsiResetBus</a> routine, which is a required entry point for all miniport drivers. The prototype for this routine is <a href="https://msdn.microsoft.com/library/windows/hardware/ff563872">PHW_RESET_BUS</a>. 


### -field HwDmaStarted

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557291">HwScsiDmaStarted</a> routine if its HBA uses system DMA, that is, a system DMA controller. Set this to <b>NULL</b> if the HBA is a bus master or uses PIO. The prototype for this routine is <a href="https://msdn.microsoft.com/library/windows/hardware/ff563860">PHW_DMA_STARTED</a>. 


### -field HwAdapterState

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557278">HwScsiAdapterState</a> routine, which is a required entry point for miniport drivers of HBAs with BIOSs that are linked with an operating system-dependent, x86-platform-only port driver that must switch between x86 protected and real processor modes. If the miniport driver needs no <i>HwScsiAdapterState</i> routine, set this member to <b>NULL</b>. A miniport driver for an HBA that has a BIOS must have a HwScsiAdapterState routine in order to be compatible with the x86-only port driver and portable to an x86-only operating system environment. The prototype for this routine is <a href="https://msdn.microsoft.com/library/windows/hardware/ff563857">PHW_ADAPTER_STATE</a>. 


### -field DeviceExtensionSize

Specifies the size in bytes required by the miniport driver for its per-HBA device extension. A miniport driver uses its device extension as storage for driver-determined HBA information. The OS-specific port driver initializes each device extension it allocates with zeros, and passes a pointer to the HBA-specific device extension in every call to a miniport driver except to its <b>DriverEntry</b> routine. The given size does not include any miniport driver-requested per-logical-unit storage, described next.


### -field SpecificLuExtensionSize

Specifies the size in bytes required by the miniport driver for its per-logical-unit storage, if any. A miniport driver can use its LU extensions as storage for driver-determined logical-unit information about SCSI peripherals on the bus. The OS-specific port driver initializes each LU extension it allocates with zeros. Leave this member set to zero if the miniport driver does not maintain per-LU information for which it requires storage. This value is based on the assumption that the HBA is able to receive 32-bit addresses, regardless of what the controller can actually support. If additional space is needed in the LUN or SRB extensions to handle 64-bit addresses, then appropriate adjustments must be made to this value before using it with routines such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff564639">ScsiPortGetUncachedExtension</a>.


### -field SrbExtensionSize

Specifies the size in bytes required by the miniport driver for its per-request storage, if any. A miniport driver can use SRB extensions as storage for driver-determined, request-specific information, such as data necessary to process a particular request. The OS-specific port driver does not initialize SRB extensions, but sets a pointer to this storage in each SRB it sends to the miniport driver. An SRB extension can be safely accessed by the HBA hardware. Leave this member set to zero if the miniport driver does not maintain per-SRB information for which it requires storage. This value is based on the assumption that the HBA is able to receive 32-bit addresses, regardless of what the controller can actually support. If additional space is needed in the LUN or SRB extensions to handle 64-bit addresses, then appropriate adjustments must be made to this value before using it with routines such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff564639">ScsiPortGetUncachedExtension</a>.


### -field NumberOfAccessRanges

Specifies how many access ranges the adapter uses. Each is a range either of memory addresses or I/O port addresses. A typical HBA uses two ranges, one for its I/O ports and another for its device memory range.


### -field Reserved

Reserved for system use and not available for use by miniport drivers.


### -field MapBuffers

Indicates, when <b>TRUE</b>, that all data buffer addresses must be mapped to virtual addresses for access by the miniport driver. When <b>FALSE</b>, data buffer addresses do not have to be mapped to virtual addresses.


### -field NeedPhysicalAddresses

Indicates, when <b>TRUE</b>, that the miniport driver needs to translate its device, any per-LU, and any per-SRB extension addresses, as well as SRB buffer addresses, to physical addresses, as required by the HBA. When <b>FALSE</b>, none of these addresses have to be translated to physical addresses.


### -field TaggedQueuing

Indicates, when <b>TRUE</b>, that miniport driver can support SCSI tagged queuing. When <b>FALSE</b>, the miniport driver cannot support SCSI-tagged queuing.


### -field AutoRequestSense

Indicates, when <b>TRUE</b>, that the HBA can perform a request-sense operation without requiring an explicit request to do so. When <b>FALSE</b>, the HBA requires an explicit request before it can perform a request-sense operation. Only miniport drivers driving HBAs with built-in firmware to perform request-sense operations should set this member to <b>TRUE</b>.


### -field MultipleRequestPerLu

Indicates, when <b>TRUE</b>, that the miniport driver can queue multiple requests per logical unit, in particular, within the HBA. When <b>FALSE</b>, the miniport driver cannot queue multiple requests per logical unit. Note that an HBA must support auto request sense for its miniport driver to enable this functionality. If a miniport driver sets this member to <b>TRUE</b>, it must use each SRB <b>QueueTag</b> member for requests of this type, but the SRB_FLAGS_QUEUE_ACTION_ENABLE is not set in the <b>SrbFlags</b> member of the SCSI_REQUEST_BLOCK structure.


### -field ReceiveEvent

Indicates, when <b>TRUE</b>, that the miniport driver drives an HBA that can support the receive-event SRB for SCSI asynchronous events. When <b>FALSE</b>, the HBA cannot support the receive-event SRB for SCSI asynchronous events.


### -field VendorIdLength

Specifies the size in bytes of the <b>VendorId</b> string, described next.


### -field VendorId

Pointer to an ASCII byte string identifying the manufacturer of the HBA. This member is irrelevant for Plug and Play drivers.

If the given <b>AdapterInterfaceType</b> is <b>PCIBus</b>, the vendor ID is a USHORT value allocated by the PCI SIG, which must be converted into a byte string by the miniport driver. For example, if the assigned PCI vendor ID value is 1001, the miniport driver-supplied <b>VendorId</b> string would be ('1', '0', '0', '1').


### -field DeviceIdLength

Specifies the size in bytes of the <b>DeviceId</b> string, described next.


### -field DeviceId

Pointer to an ASCII byte string identifying the HBA model(s) supported by the miniport driver. This member is irrelevant for Plug and Play drivers.

If the given <b>AdapterInterfaceType</b> is <b>PCIBus</b>, a device ID is a USHORT value assigned by the manufacturer of the HBA. The miniport driver must convert any PCI device ID value(s) for the HBA(s) it can support into <b>DeviceId</b> byte string(s), as for the <b>VendorId</b> member. For example, if a miniport driver can support HBAs with the PCI device IDs 8040 and 8050, it might set <b>DeviceId</b> with a pointer to the byte string ('8', '0').


### -field HwAdapterControl

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a> routine, which is a required entry point for all PnP miniport drivers. Set this to <b>NULL</b> if the miniport driver does not support Plug and Play.


#### - ReservedUshort

Reserved for system use and is not available for use by miniport drivers.


## -remarks



Each miniport driver must initialize the HW_INITIALIZATION_DATA structure with zeros before it sets the values of relevant members in this structure and calls <b>ScsiPortInitialize</b>.

The <b>Dma64BitAddresses</b> member of HW_INITIALIZATION_DATA has been eliminated in Windows 2000 (See the discussion under PORT_CONFIGURATION_DATA for further details).

Both HW_INITIALIZATION_DATA and PORT_CONFIGURATION_INFORMATION have a pair of members called <b>SpecificLuExtensionSize</b> and <b>SrbExtensionSize</b> whose values are handled differently than they were prior to Windows 2000. The miniport driver must calculate the initial values of <b>SpecificLuExtensionSize</b> and <b>SrbExtensionSize</b> in HW_INITIALIZATION_DATA based on the assumption that the HBA is capable of handling 32-bit addresses, regardless of what the controller can actually support. (See the discussion under PORT_CONFIGURATION_DATA for further details.) 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552654">DriverEntry of SCSI Miniport Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557302">HwScsiInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564645">ScsiPortInitialize</a>
 

 

