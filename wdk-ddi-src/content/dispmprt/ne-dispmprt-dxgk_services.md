---
UID: NE:dispmprt.DXGK_SERVICES
title: DXGK_SERVICES (dispmprt.h)
description: Learn more about the DXGK_SERVICES enumeration.
tech.root: display
ms.date: 04/05/2024
keywords: ["DXGK_SERVICES enumeration"]
req.header: dispmprt.h
req.construct-type: enumeration
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

# DXGK_SERVICES enumeration (dispmprt.h)



## -description

A **DXGK_SERVICES** enumeration value indicates the type of display port driver-implemented service interface that [**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md) should return.

## -enum-fields

### -field DxgkServicesAgp

Indicates the [Accelerated Graphics Port (AGP) interface](ns-dispmprt-_dxgk_agp_interface.md).

### -field DxgkServicesDebugReport

Indicates the [Debug Report interface](ns-dispmprt-_dxgk_debug_report_interface.md).

### -field DxgkServicesTimedOperation

Indicates the [Timed Operation interface](ns-dispmprt-_dxgk_timed_operation_interface.md).

### -field DxgkServicesSPB

Indicates the [Simple Peripheral Bus (SPB) interface](ns-dispmprt-_dxgk_spb_interface.md). Available starting with Windows 8.

### -field DxgkServicesBDD

Reserved for system use. Do not use in your driver. Supported starting with Windows 8.

### -field DxgkServicesFirmwareTable

Indicates the [System Firmware Table interface](ns-dispmprt-_dxgk_firmware_table_interface.md). Available starting with Windows 8.

### -field DxgkServicesIDD

Reserved for system use. Do not use in your driver. Available starting with Windows 8.

### -field DxgkServicesFeature

Indicates the [interface for querying whether a feature is enabled](ns-dispmprt-dxgk_feature_interface.md). Available starting with Windows 11, version 24H2 (WDDM 3.2).

## -remarks

In this context, an interface is a set of pointers to functions implemented by *Dxgkrnl*. A kernel-mode display minport driver (KMD) can call the function interfaces that aren't reserved for system use.

## -see-also

[**DXGK_AGP_INTERFACE**](ns-dispmprt-_dxgk_agp_interface.md)

[**DXGK_DEBUG_REPORT_INTERFACE**](ns-dispmprt-_dxgk_debug_report_interface.md)

[**DXGK_FIRMWARE_TABLE_INTERFACE**](ns-dispmprt-_dxgk_firmware_table_interface.md)

[**DXGK_FEATURE_INTERFACE**](ns-dispmprt-dxgk_feature_interface.md)

[**DXGK_SPB_INTERFACE**](ns-dispmprt-_dxgk_spb_interface.md)

[**DXGK_TIMED_OPERATION_INTERFACE**](ns-dispmprt-_dxgk_timed_operation_interface.md)

[**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md)
