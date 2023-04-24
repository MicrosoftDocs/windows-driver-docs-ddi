---
UID: NF:oprghdlr.DeRegisterOpRegionHandler
title: DeRegisterOpRegionHandler function (oprghdlr.h)
description: The DeRegisterOpRegionHandler routine deregisters an operation region handler with the ACPI driver.
tech.root: acpi
ms.date: 03/03/2023
keywords: ["DeRegisterOpRegionHandler function"]
ms.keywords: DeRegisterOpRegionHandler, DeRegisterOpRegionHandler routine [ACPI Devices], acpi.deregisteropregionhandler, opregref_e991e152-6162-4d45-9418-282afb447d18.xml, oprghdlr/DeRegisterOpRegionHandler
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
req.typenames: 
f1_keywords:
 - DeRegisterOpRegionHandler
 - oprghdlr/DeRegisterOpRegionHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Oprghdlr.lib
 - Oprghdlr.dll
api_name:
 - DeRegisterOpRegionHandler
---

## -description

The **DeRegisterOpRegionHandler** routine deregisters an operation region handler with the [ACPI driver](/windows-hardware/drivers/kernel/acpi-driver).

## -parameters

### -param DeviceObject [in]

Pointer to the physical device object (PDO) that represents the ACPI device that defines the operation region.

### -param OperationRegionObject [in]

Specifies the operation region object returned by [RegisterOpRegionHandler](./nf-oprghdlr-registeropregionhandler.md) for the operation region handler.

## -returns

Returns one of the following status values.

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The operating region handler was successfully registered. |
| **STATUS_INSUFFICIENT_RESOURCES** | The routine could not allocate the necessary system resources. |
| **STATUS_Xxx** | An internal error occurred. |

## -remarks

This routine is used in combination with [RegisterOpRegionHandler](./nf-oprghdlr-registeropregionhandler.md). To deregister an operation region handler, the caller must specify the operation region object returned by **RegisterOpRegionHandler** when it registered the operation region handler.

For more information about operation regions, see [Supporting an Operation Region](/windows-hardware/drivers/acpi/supporting-an-operation-region).

## -see-also

[ACPI_OP_REGION_HANDLER](./nc-oprghdlr-acpi_op_region_handler.md)

[RegisterOpRegionHandler](./nf-oprghdlr-registeropregionhandler.md)