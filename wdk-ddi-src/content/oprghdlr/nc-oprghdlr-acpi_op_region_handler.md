---
UID: NC:oprghdlr.ACPI_OP_REGION_HANDLER
title: ACPI_OP_REGION_HANDLER (oprghdlr.h)
description: An ACPI_OP_REGION_HANDLER-typed routine is supplied by an ACPI device function driver to provide access by the ACPI driver to the device's operation region.
old-location: acpi\pacpi_op_region_handler.htm
tech.root: acpi
ms.assetid: c3a5af59-c97c-42be-bc43-afa30ad710ec
ms.date: 08/20/2020
keywords: ["ACPI_OP_REGION_HANDLER callback function"]
ms.keywords: ACPI_OP_REGION_HANDLER, ACPI_OP_REGION_HANDLER callback, AcpiOpRegionHandler, AcpiOpRegionHandler callback function [ACPI Devices], acpi.pacpi_op_region_handler, opregref_be7bf2cd-0369-4efd-bbdb-5ad7dc28c33d.xml, oprghdlr/AcpiOpRegionHandler
f1_keywords:
 - "oprghdlr/AcpiOpRegionHandler"
 - "AcpiOpRegionHandler"
req.header: oprghdlr.h
req.include-header: Oprghdlr.h
req.target-type: Desktop
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
req.irql: (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- oprghdlr.h
api_name:
- AcpiOpRegionHandler
targetos: Windows
req.typenames: 
---

# ACPI_OP_REGION_HANDLER callback function

## -description

An ACPI_OP_REGION_HANDLER-typed routine is supplied by an ACPI device function driver to provide access by the [ACPI driver](https://docs.microsoft.com/windows-hardware/drivers/kernel/acpi-driver) to the device's operation region.

## -parameters

### -param AccessType

Specifies one of the following access types:

| Access type | Description |
|--|--|
| ACPI_OPREGION_WRITE | Write to the operation region memory buffer. |
| ACPI_OPREGION_READ | Read from the operation region memory buffer. |

### -param OperationRegionObject

Specifies the operation region object returned by [RegisterOpRegionHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nf-oprghdlr-registeropregionhandler) for the operation region handler.

### -param Address

Specifies a byte offset in the operation region memory buffer. Depending on the access type, data is transferred to or from this memory location.

### -param Size

Specifies the number of bytes to access.

### -param Data

Pointer to the data buffer supplied by the ACPI driver that is associated with the access. For a read access, bytes are transferred from the operation region memory buffer to the data buffer. For a write access, bytes are transferred from the data buffer to the operation region memory buffer.

### -param Context

Pointer to the same operation region context that the function driver specified when it registered the operation region handler.

### -param CompletionHandler

Reserved for internal use.

### -param CompletionContext

Reserved for internal use.

## -returns

Returns one of the following status values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The access was successful. |
| STATUS_INVALID_DEVICE_REQUEST | The access type is invalid. |
| STATUS_Xxx | An internal error occurred. |

## -remarks

When the ACPI driver calls an operation region handler, it specifies values for *Address* and *Size* that ensure that the access is within the operation region that is defined in the ACPI BIOS for the ACPI device. The ACPI device function driver must ensure that the operation region memory buffer it allocates is at least as large, in bytes, as the operation region defined for the ACPI device.

For more information about operation region handlers, see [Supporting an Operation Region](https://docs.microsoft.com/windows-hardware/drivers/acpi/supporting-an-operation-region).

An ACPI_OP_REGION_HANDLER-typed routine runs at the caller's IRQL.

For detailed information about constraints on operation regions, see the [Advanced Configuration and Power Interface (ACPI) Specification](https://uefi.org/specifications).

## -see-also

[DeRegisterOpRegionHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nf-oprghdlr-deregisteropregionhandler)

[RegisterOpRegionHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nf-oprghdlr-registeropregionhandler)
