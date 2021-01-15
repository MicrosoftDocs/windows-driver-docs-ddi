---
UID: NS:ntddk._WHEA_GENERIC_ERROR_DESCRIPTOR
title: _WHEA_GENERIC_ERROR_DESCRIPTOR (ntddk.h)
description: The WHEA_GENERIC_ERROR_DESCRIPTOR structure describes a generic error source.
old-location: whea\whea_generic_error_descriptor.htm
tech.root: whea
ms.date: 02/20/2018
keywords: ["WHEA_GENERIC_ERROR_DESCRIPTOR structure"]
ms.keywords: "*PWHEA_GENERIC_ERROR_DESCRIPTOR, PWHEA_GENERIC_ERROR_DESCRIPTOR, PWHEA_GENERIC_ERROR_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_GENERIC_ERROR_DESCRIPTOR, WHEA_GENERIC_ERROR_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_GENERIC_ERROR_DESCRIPTOR, ntddk/PWHEA_GENERIC_ERROR_DESCRIPTOR, ntddk/WHEA_GENERIC_ERROR_DESCRIPTOR, whea.whea_generic_error_descriptor, whearef_f9183d24-a7ad-4328-99b3-6e23ff890d1b.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.typenames: WHEA_GENERIC_ERROR_DESCRIPTOR, *PWHEA_GENERIC_ERROR_DESCRIPTOR
f1_keywords:
 - _WHEA_GENERIC_ERROR_DESCRIPTOR
 - ntddk/_WHEA_GENERIC_ERROR_DESCRIPTOR
 - PWHEA_GENERIC_ERROR_DESCRIPTOR
 - ntddk/PWHEA_GENERIC_ERROR_DESCRIPTOR
 - WHEA_GENERIC_ERROR_DESCRIPTOR
 - ntddk/WHEA_GENERIC_ERROR_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_GENERIC_ERROR_DESCRIPTOR
 - PWHEA_GENERIC_ERROR_DESCRIPTOR
 - WHEA_GENERIC_ERROR_DESCRIPTOR
---

# _WHEA_GENERIC_ERROR_DESCRIPTOR structure


## -description

The WHEA_GENERIC_ERROR_DESCRIPTOR structure describes a generic error source.

## -struct-fields

### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_GENERIC.

### -field Reserved

Reserved for system use.

### -field Enabled

A Boolean value that indicates if the error source is enabled.

### -field ErrStatusBlockLength

The size, in bytes, of the block of error status registers that contain the error data for the error source.

### -field RelatedErrorSourceId

The identifier of the related error source. If the generic error source does not relate back to another error source, this member is not used.

### -field ErrStatusAddressSpaceID

The address space of the address that is specified in the <b>ErrStatusAddress</b> member. Possible values are:





#### 0x00

System memory space



#### 0x01

System I/O space



#### 0x02

PCI configuration space



#### 0x03

Embedded controller address space



#### 0x04

System management bus (SMBus) address space



#### 0x05 - 0x7E

Reserved



#### 0x7F

Functional fixed hardware address space



#### 0x80 - 0xBF

Reserved



#### 0xC0 - 0xFF

OEM defined address space

### -field ErrStatusAddressBitWidth

The size, in bits, of the register at the address that is specified in the <b>ErrStatusAddress</b> member.

### -field ErrStatusAddressBitOffset

The offset, in bits, of the register at the address that is specified in the <b>ErrStatusAddress</b> member.

### -field ErrStatusAddressAccessSize

The access size for reading the register at the address that is specified in the <b>ErrStatusAddress</b> member. Possible values are:





#### 0

Undefined



#### 1

Byte access



#### 2

Word access



#### 3

Double word access



#### 4

Quad word access

### -field ErrStatusAddress

The 64-bit address of a register that contains the physical address of a block of memory that contains the error status data for the error source. This block of memory must reside in firmware reserved memory so that it is not reclaimed by the operating system's memory manager. The error status data contained in this block of memory is described by a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error">WHEA_GENERIC_ERROR</a> structure.

### -field Notify

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_notification_descriptor">WHEA_NOTIFICATION_DESCRIPTOR</a> structure that describes the notification mechanism that is used by the error source.

## -remarks

A WHEA_GENERIC_ERROR_DESCRIPTOR structure is contained within the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error">WHEA_GENERIC_ERROR</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_notification_descriptor">WHEA_NOTIFICATION_DESCRIPTOR</a>

