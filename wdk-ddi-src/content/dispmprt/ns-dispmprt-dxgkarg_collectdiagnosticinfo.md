---
UID: NS:dispmprt._DXGKARG_COLLECTDIAGNOSTICINFO
title: DXGKARG_COLLECTDIAGNOSTICINFO
author: windows-driver-content
description: Used by the DXGKDDI_COLLECTDIAGNOSTICINFO callback function to collect private driver information for a variety of reasons.
tech.root: display
ms.assetid: 04b03acc-2025-4e79-bb7b-46adb7492256
ms.author: windowsdriverdev
ms.date: 03/24/2020
keywords: ["DXGKARG_COLLECTDIAGNOSTICINFO structure"]
ms.keywords: DXGKARG_COLLECTDIAGNOSTICINFO, DXGKARG_COLLECTDIAGNOSTICINFO, *INOUT_PDXGKARG_COLLECTDIAGNOSTICINFO
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_COLLECTDIAGNOSTICINFO
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_COLLECTDIAGNOSTICINFO
 - dispmprt/_DXGKARG_COLLECTDIAGNOSTICINFO
 - DXGKARG_COLLECTDIAGNOSTICINFO
 - dispmprt/DXGKARG_COLLECTDIAGNOSTICINFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - DXGKARG_COLLECTDIAGNOSTICINFO
dev_langs:
 - c++
---

# DXGKARG_COLLECTDIAGNOSTICINFO structure


## -description

Used by the [DXGKDDI_COLLECTDIAGNOSTICINFO](nc-dispmprt-dxgkddi_collectdiagnosticinfo.md) callback function to collect private driver information for a variety of reasons.

For example, the OS will call the DXGKDDI_COLLECTDIAGNOSTICINFO callback function when diagnostic information is needed, while providing the type of information being requested ([DXGK_DIAGNOSTICINFO_TYPE](ne-dispmprt-dxgk_diagnosticinfo_type.md)). The driver should collect all private information to investigate the issue and submit it to the OS.

## -struct-fields

### -field hAdapter

[in, optional] A handle to a context block associated with a display adapter.

Prior to WDDM 2.6, the display miniport driver's [DxgkDdiAddDevice](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function provided this handle to the DirectX graphics kernel subsystem. This parameter is optional and can be NULL if the driver failed to provide the handle to the OS.

### -field Type

[in] A [DXGK_DIAGNOSTICINFO_TYPE](ne-dispmprt-dxgk_diagnosticinfo_type.md) enumeration value that indicates the type of information the driver needs to collect.

### -field BucketingString

[out] A fixed size buffer provided for a string that the driver should use to identify the issue for bucketing purposes. This string should be consistent between driver versions for the same issue so it should not contain elements such as source references, driver versions, or instance specific details like fence numbers or target ids. It may contain information such as an identifier of the internal sub-component which failed, or the name of a module, for example `mismatched_driver_ihvxseries.sys`. The valid codes are `0x21-0x7E` and the underscore (`0x5f`) should be used instead of the space (`0x20`).

### -field DescriptionString

[out, optional] A fixed size buffer provided for a string that the driver should use to describe instance specific details which are not used for bucketing, but may be used to give more details about a specific issue, for example `mismatched_driver_versions_kmd_10.22.1111.1121,_ihvxseries:10.22.1111.1122`. The valid codes are `0x21-0x7E` and the underscore (`0x5f`) should be used instead of the space (`0x20`).

### -field pReserved

[out, optional] A pointer to VOID in an unnamed union that is reserved as a placeholder for a pointer to a type-specific argument the OS might supply for some *Types*. This value is NULL for *Types* which don’t require any extended information.

### -field BufferSizeIn

[in] A variable that provides the size, in bytes, of the OS allocated buffer. For *Type* value of **DXGK_DI_ADDDEVICE** and **DXGK_DI_STARTDEVICE** the size will be around 0x80000.

### -field BufferSizeOut

[out] A variable that the driver should update with an actual size filled with its private data. If no private data is provided, the driver should assign 0 to the variable.

### -field pBuffer

[out] A pointer to a buffer that receives the private driver data.

## -remarks

## -see-also

[DXGK_DIAGNOSTICINFO_TYPE](ne-dispmprt-dxgk_diagnosticinfo_type.md)

[DXGKDDI_COLLECTDIAGNOSTICINFO](nc-dispmprt-dxgkddi_collectdiagnosticinfo.md)

[DxgkDdiAddDevice](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)

