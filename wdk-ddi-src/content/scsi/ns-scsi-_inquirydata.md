---
UID: NS:scsi._INQUIRYDATA
title: INQUIRYDATA (scsi.h)
description: The INQUIRYDATA structure (scsi.h) contains information about the SCSI inquiry data associated with a tape device.
tech.root: storage
ms.date: 09/20/2022
keywords: ["INQUIRYDATA structure"]
ms.keywords: "*PINQUIRYDATA, INQUIRYDATA, INQUIRYDATA structure [Storage Devices], PINQUIRYDATA, PINQUIRYDATA structure pointer [Storage Devices], _INQUIRYDATA, scsi/INQUIRYDATA, scsi/PINQUIRYDATA, storage.inquirydata, structs-tape_be59bcac-0d77-4186-99a6-97c34bb37793.xml"
req.header: scsi.h
req.include-header: Scsi.h, Minitape.h, Storport.h
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
req.typenames: INQUIRYDATA, *PINQUIRYDATA
f1_keywords:
 - _INQUIRYDATA
 - scsi/_INQUIRYDATA
 - PINQUIRYDATA
 - scsi/PINQUIRYDATA
 - INQUIRYDATA
 - scsi/INQUIRYDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - _INQUIRYDATA
 - PINQUIRYDATA
 - INQUIRYDATA
---
## -description

The **INQUIRYDATA** structure is used in conjunction with the [TapeMiniExtensionInit](/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_extension_init_routine) and [TapeMiniVerifyInquiry](/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_verify_inquiry_routine) routines to report SCSI inquiry data associated with a tape device.

## -struct-fields

### -field DeviceType

Specifies the type of device. For a complete list of symbolic constants that indicate the various device types, see [Specifying Device Types](/windows-hardware/drivers/kernel/specifying-device-types).

### -field DeviceTypeQualifier

Indicates whether the device is present or not. The values that this member can take are as follows:

| Value | Meaning |
|--|--|
| DEVICE_QUALIFIER_ACTIVE | The operating system supports the device, and the device is present. |
| DEVICE_QUALIFIER_NOT_ACTIVE | The operating system supports the device, but the device is not present. |
| DEVICE_QUALIFIER_NOT_SUPPORTED | The operating system does not support this device. |

### -field DeviceTypeModifier

Specifies the device type modifier, if any, as defined by SCSI. If no device type modifier exists, this member is zero.

### -field RemovableMedia

Indicates, when **TRUE**, that the media is removable, and when **FALSE** that the media is not removable.

### -field Versions

Indicates the version of the inquiry data standard that this data conforms to. For more information about the version values allowed in this field, see the *SCSI Primary Commands - 2 (SPC-2)* specification.

### -field ResponseDataFormat

Indicates the SCSI standard that governs the response data format. The value of this member must be 2.

### -field HiSupport

Indicates, when zero, that the target does not use the hierarchical addressing model to assign LUNs to logical units. A value of 1 indicates the target uses the hierarchical addressing model to assign LUNs to logical units.

### -field NormACA

Indicates, when set to one, that the operating system supports setting the NACA bit to one in the control byte of the command descriptor block (CDB). A value of zero indicates that the system does not support setting the NACA bit to one. For more information about the function of the NACA bit and the control byte in a CDB, see the *SCSI Primary Commands - 2 (SPC-2)* specification.

### -field ReservedBit

Reserved.

### -field AERC

Indicates, when set to one, that the target device supports the asynchronous event reporting capability. A value of zero indicates that the target device does not support asynchronous event reports. Details of the asynchronous event reporting support are protocol-specific. For more information about asynchronous even reporting, see the *SCSI Primary Commands - 2 (SPC-2)* specification.

### -field AdditionalLength

Specifies the length in bytes of the parameters of the command descriptor block (CDB).

### -field Reserved[2]

Reserved.

### -field SoftReset

Indicates, when set to one, that the target device supports soft resets. A value of zero indicates that the target does not support soft resets.

### -field CommandQueue

Indicates, when set to one, that the target device supports command queuing for this logical unit. However, a value of zero does not necessarily indicate that the target device does not support command queuing. The meaning of these values depends on the values present in the SCSI inquiry data. For information about the meaning of the command queuing bit, see the *SCSI Primary Commands - 2 (SPC-2)* specification.

### -field Reserved2

Reserved.

### -field LinkedCommands

Indicates, when set to one, that the operating system supports linked commands. A value of zero indicates the operating system does not support linked commands.

### -field Synchronous

Indicates, when set to one, that the target supports synchronous data transfer. A value of zero indicates that the target does not support synchronous data transfer.

### -field Wide16Bit

Indicates, when set to one, that the target supports 16-bit wide data transfers. A value of zero indicates that the device does not support 16-bit wide data transfers.

### -field Wide32Bit

Indicates, when set to one, that the target supports 32-bit wide data transfers. A value of zero indicates that the device does not support 32-bit wide data transfers.

### -field RelativeAddressing

Indicates, when set to one, that the operating system supports the relative addressing mode. A value of zero indicates the operating system does not support relative addressing.

### -field VendorId[8]

Contains eight bytes of ASCII data that identifies the vendor of the product.

### -field ProductId[16]

Contains sixteen bytes of ASCII data that indicates the product ID, as defined by the vendor. The data shall be left-aligned within this field and the unused bytes filled with ASCII blanks.

### -field ProductRevisionLevel[4]

Contains four bytes of ASCII data that indicates the product revision level, as defined by the vendor.

### -field VendorSpecific[20]

Contains 20 bytes of vendor-specific data.

### -field Reserved3[2]

Reserved.

### -field VersionDescriptors[8]

Defines the **UCHAR** member **VersionDescriptors[8]**.

### -field Reserved4[30]

Reserved.

## -remarks

Additional members defined within the #else conditional directive in the structure definition in scsi.h.

### ANSIVersion

Indicates the ANSI version of the inquiry data standard that this data conforms to. For more information about the version values allowed in this field, see the *SCSI Primary Commands - 2 (SPC-2)* specification.

### ECMAVersion

Indicates the ECMA version of the inquiry data standard that this data conforms to. For more information about the version values allowed in this field, see the *SCSI Primary Commands - 2 (SPC-2)* specification.

### ISOVersion

Indicates the ISO version of the inquiry data standard that this data conforms to. For more information about the version values allowed in this field, see the *SCSI Primary Commands - 2 (SPC-2)* specification.

### TerminateTask

Indicates, when set to one, that the target device supports the SCSI TERMINATE TASK task management function. A value of zero indicates that the target device does not support the TERMINATE TASK task management function.

### Addr16

Indicates, when set to one, that the target supports 16-bit wide SCSI addresses. A value of zero indicates that the device does not support 32-bit wide SCSI addresses.

### Addr32

Indicates, when set to one, that the target supports 32-bit wide SCSI addresses. A value of zero indicates that the device does not support 32-bit wide SCSI addresses.

### AckReqQ

Indicates, when set to one, that the target supports a request and acknowledge data transfer handshake on the secondary bus. A value of zero indicates that the target does not support this function.

### MediumChanger

Indicates, when set to one, that the device is embedded within or attached to a medium transport element. A value of zero indicates that the device is not embedded within or attached to a medium transport element.

### MultiPort

Indicates, when set to one, that the target device is a multiport (2 or more ports) device that conforms to the SCSI-3 multiport device requirements. A value of zero indicates that this device has a single port and does not implement the multiport requirements.

### ReservedBit2

Reserved.

### EnclosureServices

Indicates, when set to one, that the device contains an embedded enclosure services component. A value of zero indicates that the device does not contain an embedded enclosure services component.

### ReservedBit3

Reserved.

### TransferDisable

Indicates, when set to one, that the target supports the SCSI CONTINUE TASK and TARGET TRANSFER DISABLE messages. A value of zero indicates that the device does not support one or both of these messages.  For more information about the CONTINUE TASK and TARGET TRANSFER DISABLE messages, see the *SCSI Primary Commands - 2 (SPC-2)* specification.

## -see-also

[TapeMiniExtensionInit](/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_extension_init_routine)

[TapeMiniVerifyInquiry](/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_verify_inquiry_routine)
