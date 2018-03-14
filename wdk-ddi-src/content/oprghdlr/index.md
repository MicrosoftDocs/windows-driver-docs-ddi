---
UID: NA:oprghdlr
ms.assetid: e673a615-101a-3857-b1ee-6c84b25974ac
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Oprghdlr.h header



This header is used by ACPI. For more information, see
- [ACPI](../_acpi/index.md)

Oprghdlr.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [DeRegisterOpRegionHandler function](nf-oprghdlr-deregisteropregionhandler.md) | The DeRegisterOpRegionHandler routine deregisters an operation region handler with the ACPI driver. |
| [RegisterOpRegionHandler function](nf-oprghdlr-registeropregionhandler.md) | The RegisterOpRegionHandler routine registers an operation region handler with the ACPI driver. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [ACPI_OP_REGION_HANDLER callback](nc-oprghdlr-acpi_op_region_handler.md) | An ACPI_OP_REGION_HANDLER-typed routine is supplied by an ACPI device function driver to provide access by the ACPI driver to the device's operation region. |
