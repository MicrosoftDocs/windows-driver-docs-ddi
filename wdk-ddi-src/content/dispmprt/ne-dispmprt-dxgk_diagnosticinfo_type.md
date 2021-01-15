---
UID: NE:dispmprt._DXGK_DIAGNOSTICINFO_TYPE
title: DXGK_DIAGNOSTICINFO_TYPE
description: Indicates the type of information the driver needs to collect.
tech.root: display
ms.date: 03/24/2020
keywords: ["DXGK_DIAGNOSTICINFO_TYPE enumeration"]
ms.keywords: DXGK_DIAGNOSTICINFO_TYPE, DXGK_DIAGNOSTICINFO_TYPE,
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: DXGK_DIAGNOSTICINFO_TYPE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGK_DIAGNOSTICINFO_TYPE
 - dispmprt/_DXGK_DIAGNOSTICINFO_TYPE
 - DXGK_DIAGNOSTICINFO_TYPE
 - dispmprt/DXGK_DIAGNOSTICINFO_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAGNOSTICINFO_TYPE
 - DXGK_DIAGNOSTICINFO_TYPE
dev_langs:
 - c++
---

# DXGK_DIAGNOSTICINFO_TYPE enumeration


## -description

Indicates the type of information the driver needs to collect.

## -enum-fields

### -field DXGK_DI_ADDDEVICE

The type of information to be collected for [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md).

### -field DXGK_DI_STARTDEVICE

The type of information to be collected for [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md).

### -field DXGK_DDI_BLACKSCREEN

Collect black box data for black screen scenarios in calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md) and [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md). DXGK_DDI_BLACKSCREEN is available in Windows 10, version 2004 and later versions. WDDM 2.7 and later drivers are required to support this value.

## -remarks

## -see-also

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)

