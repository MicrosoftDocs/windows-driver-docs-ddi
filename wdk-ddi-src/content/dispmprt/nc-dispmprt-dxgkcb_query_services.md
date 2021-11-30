---
UID: NC:dispmprt.DXGKCB_QUERY_SERVICES
title: DXGKCB_QUERY_SERVICES (dispmprt.h)
description: The DxgkCbQueryServices function returns an interface implemented by the display port driver.
old-location: display\dxgkcbqueryservices.htm
tech.root: display
ms.date: 11/18/2021
keywords: ["DXGKCB_QUERY_SERVICES callback function"]
ms.keywords: DXGKCB_QUERY_SERVICES, DXGKCB_QUERY_SERVICES callback, DpFunctions_1bf190e2-3bfc-4ea9-942a-502ec71fa362.xml, DxgkCbQueryServices, DxgkCbQueryServices callback function [Display Devices], display.dxgkcbqueryservices, dispmprt/DxgkCbQueryServices
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKCB_QUERY_SERVICES
 - dispmprt/DXGKCB_QUERY_SERVICES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKCB_QUERY_SERVICES
---

# DXGKCB_QUERY_SERVICES callback function

## -description

The **DxgkCbQueryServices** function returns an interface implemented by the display port driver.

## -parameters

### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](ns-dispmprt-_dxgkrnl_interface.md) structure that was passed to [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md).

### -param ServicesType [in]

A constant from the [**DXGK_SERVICES**](ne-dispmprt-dxgk_services.md) enumeration that specifies which interface is being requested.

### -param Interface [in, out]

A pointer to an [**INTERFACE**](../wdm/ns-wdm-_interface.md) structure that receives the requested interface.

## -returns

**DxgkCbQueryServices** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

An interface, in this context, is a set of functions implemented by the display port driver. The display port driver makes the functions of an interface available to other drivers by providing function pointers in response to **DxgkCbQueryServices**.

### Obtaining the AGP interface

To obtain an Accelerated Graphics Port (AGP) interface, do the following:

1. Allocate a [**DXGK_AGP_INTERFACE**](ns-dispmprt-_dxgk_agp_interface.md) structure.

2. Set the **Size** member to sizeof(DXGK_AGP_INTERFACE).

3. Set the **Version** member. Version constants are defined in *Dispmprt.h* (for example, DXGK_AGP_INTERFACE_VERSION_1).

4. Call **DxgkCbQueryServices**; set **ServicesType** to **DxgkServicesAgp**, and set **Interface** to the address (cast as [PINTERFACE](../wdm/ns-wdm-_interface.md)) of your **DXGK_AGP_INTERFACE** structure.

5. On return from **DxgkCbQueryServices**, your **DXGK_AGP_INTERFACE** structure will contain pointers to the AGP interface functions; for example, [**AgpAllocatePool**](nc-dispmprt-dxgkcb_agp_allocate_pool.md).

### Obtaining the Debug Report interface

To obtain a Debug Report interface, do the following:

1. Allocate a [**DXGK_DEBUG_REPORT_INTERFACE**](ns-dispmprt-_dxgk_debug_report_interface.md) structure.

2. Set the **Size** member to sizeof(DXGK_DEBUG_REPORT_INTERFACE).

3. Set the **Version** member. Version constants are defined in *Dispmprt.h* (for example,  DXGK_DEBUG_REPORT_INTERFACE_VERSION_1).

4. Call **DxgkCbQueryServices**; set **ServicesType** to **DxgkServicesDebugReport**, and set **Interface** to the address (cast as PINTERFACE) of your **DXGK_DEBUG_REPORT_INTERFACE** structure.

5. On return from **DxgkCbQueryServices**, your DXGK_DEBUG_REPORT_INTERFACE structure will contain pointers to the Debug Report interface functions; for example, [**DbgReportCreate**](ns-dispmprt-_dxgk_debug_report_interface.md).

### Obtaining the Timed Operation interface

To obtain a Timed Operation interface, do the following:

1. Allocate a [**DXGK_TIMED_OPERATION_INTERFACE**](ns-dispmprt-_dxgk_timed_operation_interface.md) structure.

2. Set the **Size** member to sizeof(DXGK_TIMED_OPERATION_INTERFACE).

3. Set the **Version** member. Version constants are defined in *Dispmprt.h* (for example,  DXGK_TIMED_OPERATION_INTERFACE_VERSION_1).

4. Call **DxgkCbQueryServices**; set **ServicesType** to **DxgkServicesTimedOperation**, and set **Interface** to the address (cast as PINTERFACE) of your **DXGK_TIMED_OPERATION_INTERFACE** structure.

5. On return from **DxgkCbQueryServices**, your **DXGK_TIMED_OPERATION_INTERFACE** structure will contain pointers to the Timed Operation interface functions; for example, [**TimedOperationStart**](ns-dispmprt-_dxgk_timed_operation_interface.md).

### Obtaining the SPB and System Firmware Table interfaces

The [Simple Peripheral Bus (SPB)](ns-dispmprt-_dxgk_spb_interface.md) and [System Firmware Table](ns-dispmprt-_dxgk_firmware_table_interface.md) interfaces can be similarly obtained by following the above steps using the appropriate **ServicesType** and structure.

## -see-also

[**DXGK_AGP_INTERFACE**](ns-dispmprt-_dxgk_agp_interface.md)

[**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md)

[**DXGK_DEBUG_REPORT_INTERFACE**](ns-dispmprt-_dxgk_debug_report_interface.md)

[**DXGK_FIRMWARE_TABLE_INTERFACE**](ns-dispmprt-_dxgk_firmware_table_interface.md)

[**DXGK_SERVICES**](ne-dispmprt-dxgk_services.md)

[**DXGK_SPB_INTERFACE**](ns-dispmprt-_dxgk_spb_interface.md)

[**DXGK_TIMED_OPERATION_INTERFACE**](ns-dispmprt-_dxgk_timed_operation_interface.md)

[**DXGKRNL_INTERFACE**](ns-dispmprt-_dxgkrnl_interface.md)

[**INTERFACE**](../wdm/ns-wdm-_interface.md)