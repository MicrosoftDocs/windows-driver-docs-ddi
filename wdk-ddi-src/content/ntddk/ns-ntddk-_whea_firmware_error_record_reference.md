---
UID: NS:ntddk._WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
title: _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE (ntddk.h)
description: The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes a reference to a firmware error record that is specific to the Itanium processor architecture.
tech.root: whea
ms.date: 03/13/2023
keywords: ["WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure"]
ms.keywords: "*PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, *PWHEA_FIRMWARE_RECORD, PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure pointer [WHEA Drivers and Applications], WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure [WHEA Drivers and Applications], WHEA_FIRMWARE_RECORD, _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, ntddk/PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, ntddk/WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, whea.whea_firmware_error_record_reference, whearef_b43d8c6f-f768-47a1-9494-4a4bfac7d586.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.typenames: WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, *PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE
f1_keywords:
 - _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - ntddk/_WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - ntddk/PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - ntddk/WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE
 - WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
---

## -description

The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes a reference to a firmware error record that is specific to the Itanium processor architecture.

## -struct-fields

### -field Type

The type of firmware error record. This member is always set to WHEA_FIRMWARE_RECORD_TYPE_IPFSAL.

### -field Reserved

Reserved for system use.

### -field FirmwareRecordId

The identifier of the firmware error record.

## -remarks

The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes the data that is contained in an Itanium processor firmware error record reference section of an [error record](/windows-hardware/drivers/whea/error-records). An error record contains an Itanium processor firmware error record reference section only if the **SectionType** member of one of the [WHEA_ERROR_RECORD_SECTION_DESCRIPTOR](./ns-ntddk-_whea_error_record_section_descriptor.md) structures that describe the error record sections for that error record contains FIRMWARE_ERROR_RECORD_REFERENCE_GUID.

The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure contains a reference to a SAL error record that was created by the system firmware. For more information about the format of a SAL error record, see the [Intel Itanium Processor Family System Abstraction Layer Specification](https://www.intel.com/content/dam/www/public/us/en/documents/specification-updates/itanium-system-abstraction-layer-specification.pdf).

## -see-also

[WHEA_ERROR_RECORD_SECTION_DESCRIPTOR](./ns-ntddk-_whea_error_record_section_descriptor.md)