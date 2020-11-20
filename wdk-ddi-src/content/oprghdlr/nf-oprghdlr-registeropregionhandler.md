---
UID: NF:oprghdlr.RegisterOpRegionHandler
title: RegisterOpRegionHandler function (oprghdlr.h)
description: The RegisterOpRegionHandler routine registers an operation region handler with the ACPI driver.
old-location: acpi\registeropregionhandler.htm
tech.root: acpi
ms.assetid: 5795a1d1-0e13-4f9f-b2f2-37bbd71bde7a
ms.date: 11/19/2020
keywords: ["RegisterOpRegionHandler function"]
ms.keywords: RegisterOpRegionHandler, RegisterOpRegionHandler routine [ACPI Devices], acpi.registeropregionhandler, opregref_9742e50b-613d-4191-b0a2-6d1b0f365494.xml, oprghdlr/RegisterOpRegionHandler
req.header: oprghdlr.h
req.include-header: Oprghdlr.h
req.target-type: Universal
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
req.lib: Oprghdlr.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: acpi
req.typenames: 
f1_keywords:
 - RegisterOpRegionHandler
 - oprghdlr/RegisterOpRegionHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Oprghdlr.lib
 - Oprghdlr.dll
api_name:
 - RegisterOpRegionHandler
---

# RegisterOpRegionHandler function

## -description

The **RegisterOpRegionHandler** routine registers an operation region handler with the [ACPI driver](/windows-hardware/drivers/kernel/acpi-driver).

## -parameters

### -param DeviceObject

[in]
Pointer to the [physical device object (PDO)](/windows-hardware/drivers/kernel/types-of-wdm-device-objects) that represents the ACPI device that defines the operation region.

### -param AccessType

[in]
Specifies ACPI_OPREGION_ACCESS_AS_COOKED.

### -param RegionSpace

[in]
Specifies one of the following types of region space.

| Region space identifier | Description |
|--|--|
| ACPI_OPREGION_REGION_SPACE_MEMORY | System memory |
| ACPI_OPREGION_REGION_SPACE_IO | I/O space |
| ACPI_OPREGION_REGION_SPACE_PCI_CONFIG | PCI configuration |
| ACPI_OPREGION_REGION_SPACE_EC | Embedded controller |
| ACPI_OPREGION_REGION_SPACE_SMB | System management bus |
| ACPI_OPREGION_REGION_SPACE_CMOS_CONFIG | CMOS configuration |
| ACPI_OPREGION_REGION_SPACE_PCIBARTARGET | PCI base address register |
| Vendor-defined value from 0x80 to 0xFF | Vendor-defined |

### -param Handler

[in]
Pointer to the [ACPI_OP_REGION_HANDLER](nc-oprghdlr-acpi_op_region_handler.md)-typed operation region handler (supplied by an ACPI device function driver).

### -param Context

[in]
Pointer to a device-specific operation region context (supplied by an ACPI device function driver).

### -param Flags

[in]
Reserved for internal use.

### -param OperationRegionObject

[out]
Pointer to caller-allocated buffer that, on output, contains a pointer to the operation region object that the ACPI driver creates for the operation region.

## -returns

Returns one of the following status values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The operating region handler was successfully registered. |
| STATUS_ACPI_INVALID_DATA | The specified information is not valid. |
| STATUS_INSUFFICIENT_RESOURCES | The routine could not allocate the necessary system resources. |
| STATUS_Xxx | An internal error occurred. |

## -remarks

The operation region context specified by *Context* is device-specific and is only used by the function driver. Typically, the context is the device extension for the [functional device object (FDO)](/windows-hardware/drivers/kernel/types-of-wdm-device-objects). The ACPI driver passes this context back to the function driver when it calls the operation region handler. The operation region object is only used by a function driver to uniquely identify the operation region when it deregisters the operation region handler.

For more information about operation regions, see [Supporting an Operation Region](/windows-hardware/drivers/acpi/supporting-an-operation-region).

## -see-also

[ACPI_OP_REGION_HANDLER](nc-oprghdlr-acpi_op_region_handler.md)

[DeRegisterOpRegionHandler](nf-oprghdlr-deregisteropregionhandler.md)
