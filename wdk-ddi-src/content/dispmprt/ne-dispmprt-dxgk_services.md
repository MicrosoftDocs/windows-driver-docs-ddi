---
UID: NE:dispmprt.__unnamed_enum_0
title: DXGK_SERVICES (dispmprt.h)
description: The DXGK_SERVICES enumeration indicates the type of interface being requested by a call to the DxgkCbQueryServices function.
old-location: display\dxgk_services.htm
tech.root: display
ms.date: 11/18/2021
keywords: ["DXGK_SERVICES enumeration"]
ms.keywords: DXGK_SERVICES, DXGK_SERVICES enumeration [Display Devices], DmEnums_340c8991-c135-47da-876d-2970157fea0b.xml, DxgkServicesAgp, DxgkServicesBDD, DxgkServicesDebugReport, DxgkServicesFirmwareTable, DxgkServicesSPB, DxgkServicesTimedOperation, display.dxgk_services, dispmprt/DXGK_SERVICES, dispmprt/DxgkServicesAgp, dispmprt/DxgkServicesBDD, dispmprt/DxgkServicesDebugReport, dispmprt/DxgkServicesFirmwareTable, dispmprt/DxgkServicesSPB, dispmprt/DxgkServicesTimedOperation
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: DXGK_SERVICES
f1_keywords:
 - DXGK_SERVICES
 - dispmprt/DXGK_SERVICES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - DXGK_SERVICES
---

# DXGK_SERVICES enumeration

## -description

The **DXGK_SERVICES** enumeration indicates the type of interface being requested by a call to the [**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md) function.

## -enum-fields

### -field DxgkServicesAgp

Indicates the [Accelerated Graphics Port (AGP) interface](ns-dispmprt-_dxgk_agp_interface.md).

### -field DxgkServicesDebugReport

Indicates the [Debug Report interface](ns-dispmprt-_dxgk_debug_report_interface.md).

### -field DxgkServicesTimedOperation

Indicates the [Timed Operation interface](ns-dispmprt-_dxgk_timed_operation_interface.md).

### -field DxgkServicesSPB

Indicates the [Simple Peripheral Bus (SPB) interface](ns-dispmprt-_dxgk_spb_interface.md). Supported starting with Windows 8.

### -field DxgkServicesBDD

Reserved for system use. Do not use in your driver. Supported starting with Windows 8.

### -field DxgkServicesFirmwareTable

Indicates the [System Firmware Table interface](ns-dispmprt-_dxgk_firmware_table_interface.md). Supported starting with Windows 8.

### -field DxgkServicesIDD

Reserved for system use. Do not use in your driver. Supported starting with Windows 8.

## -remarks

An interface, in this context, is a set of function pointers. The functions in the AGP, Debug Report, Timed Operation, SPB, and System Firmware Table interfaces are implemented by the Microsoft DirectX graphics kernel subsystem and called by the display miniport driver.

## -see-also

[**DXGK_AGP_INTERFACE**](ns-dispmprt-_dxgk_agp_interface.md)

[**DXGK_DEBUG_REPORT_INTERFACE**](ns-dispmprt-_dxgk_debug_report_interface.md)

[**DXGK_FIRMWARE_TABLE_INTERFACE**](ns-dispmprt-_dxgk_firmware_table_interface.md)

[**DXGK_SPB_INTERFACE**](ns-dispmprt-_dxgk_spb_interface.md)

[**DXGK_TIMED_OPERATION_INTERFACE**](ns-dispmprt-_dxgk_timed_operation_interface.md)
