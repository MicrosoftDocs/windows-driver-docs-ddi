---
UID: NE:dispmprt._DXGK_DIAGNOSTICINFO_TYPE
title: DXGK_DIAGNOSTICINFO_TYPE
author: windows-driver-content
description: Indicates the type of information the driver needs to collect.
tech.root: display
ms.assetid: 5f03ca69-7923-4245-89b4-7300d3ba50ab
ms.author: windowsdriverdev
ms.date: 03/24/2020
keywords: ["DXGK_DIAGNOSTICINFO_TYPE enumeration"]
f1_keywords:
 - "dispmprt/DXGK_DIAGNOSTICINFO_TYPE"
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
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - DXGK_DIAGNOSTICINFO_TYPE
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
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
