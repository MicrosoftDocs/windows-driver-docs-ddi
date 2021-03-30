---
UID: NS:ntddk._WHEA_GENERIC_ERROR_DESCRIPTOR_V2
title: WHEA_GENERIC_ERROR_DESCRIPTOR_V2
ms.date: 03/29/2021
ms.topic: language-reference
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.target-type: 
req.typenames: WHEA_GENERIC_ERROR_DESCRIPTOR_V2, *PWHEA_GENERIC_ERROR_DESCRIPTOR_V2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_GENERIC_ERROR_DESCRIPTOR_V2
 - WHEA_GENERIC_ERROR_DESCRIPTOR_V2
f1_keywords:
 - ntddk/_WHEA_GENERIC_ERROR_DESCRIPTOR_V2
 - ntddk/WHEA_GENERIC_ERROR_DESCRIPTOR_V2
dev_langs:
 - c++
---

## -description

The WHEA_GENERIC_ERROR_DESCRIPTOR_V2 structure describes a generic error source.

## -struct-fields

### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_GENERIC_V2.

### -field Reserved

Reserved for system use.

### -field Enabled

A Boolean value that indicates if the error source is enabled.

### -field ErrStatusBlockLength

The size, in bytes, of the block of error status registers that contain the error data for the error source.

### -field RelatedErrorSourceId

The identifier of the related error source. If the generic error source does not relate back to another error source, this member is not used.

### -field ErrStatusAddressSpaceID

The address space of the address that is specified in the <b>ErrStatusAddress</b> member. 


### -field ErrStatusAddressBitWidth

The size, in bits, of the register at the address that is specified in the <b>ErrStatusAddress</b> member.

### -field ErrStatusAddressBitOffset

The offset, in bits, of the register at the address that is specified in the <b>ErrStatusAddress</b> member.

### -field ErrStatusAddressAccessSize

The access size for reading the register at the address that is specified in the <b>ErrStatusAddress</b> member.

### -field ErrStatusAddress

The 64-bit address of a register that contains the physical address of a block of memory that contains the error status data for the error source. This block of memory must reside in firmware reserved memory so that it is not reclaimed by the operating system's memory manager. The error status data contained in this block of memory is described by a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error">WHEA_GENERIC_ERROR</a> structure.

### -field Notify

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_notification_descriptor">WHEA_NOTIFICATION_DESCRIPTOR</a> structure that describes the notification mechanism that is used by the error source.

### -field ReadAckAddressSpaceID

The address space of the address that is specified in the **ReadAckAddress** member.

### -field ReadAckAddressBitWidth

The size, in bits, of the register at the address that is specified in the **ReadAckAddress** member.

### -field ReadAckAddressBitOffset

The offset, in bits, of the register at the address that is specified in the **ReadAckAddress** member.

### -field ReadAckAddressAccessSize

The access size for reading the register at the address that is specified in the **ReadAckAddress** member.

### -field ReadAckAddress

The 64-bit address of a register that is used to notify the RAS controller that Windows has processed the Error Status Block.

### -field ReadAckPreserveMask

Contains a mask of bits to preserve when writing the Read Ack register.

### -field ReadAckWriteMask

Contains a mask of bits to set when writing the Read Ack register.

## -remarks

This structure corresponds to the Generic Hardware Error Source version 2 (GHESv2) structure that is defined in [Advanced Configuration and Power Interface (ACPI) Specification version 6.2](https://uefi.org/sites/default/files/resources/ACPI%206_2_A_Sept29.pdf).

## -see-also

[WHEA_ERROR_SOURCE_DESCRIPTOR](./ns-ntddk-_whea_error_source_descriptor.md)

[**WHEA_GENERIC_ERROR_DESCRIPTOR**](./ns-ntddk-_whea_generic_error_descriptor.md)
