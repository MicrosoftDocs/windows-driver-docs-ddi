---
UID: NS:iddcx.IDDCX_DISPLAYCONFIGPATH
title: IDDCX_DISPLAYCONFIGPATH
author: windows-driver-content
description: IDDCX_DISPLAYCONFIGPATH contains display monitor configuration for a path.
tech.root: display
ms.assetid: 5dce6205-f03c-4ca5-8f40-09a24eacbd13
ms.author: windowsdriverdev
ms.date: 09/20/2020
keywords: ["IDDCX_DISPLAYCONFIGPATH structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: IDDCX_DISPLAYCONFIGPATH, ,
req.header: iddcx.h
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
req.typenames: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - IDDCX_DISPLAYCONFIGPATH
 - iddcx/IDDCX_DISPLAYCONFIGPATH
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_DISPLAYCONFIGPATH
product:
 - Windows
dev_langs:
 - c++
---

# IDDCX_DISPLAYCONFIGPATH structure

## -description

**IDDCX_DISPLAYCONFIGPATH** contains the display monitor configuration for a path.

## -struct-fields

### -field Size

Size, in bytes, of this structure.

### -field MonitorObject

Monitor object handle that the driver provides to identify the monitor this path is targeted at.

### -field Position

A [**POINT**](/windows/win32/api/windef/ns-windef-point) structure containing the requested desktop position for this path.

### -field Resolution

A [**DISPLAYCONFIG_2DREGION**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_2dregion) structure containing the resolution for this path. **Resolution** must match a resolution supported by the driver.

### -field Rotation

A [**DISPLAYCONFIG_ROTATION**](/windows/win32/api/wingdi/ne-wingdi-displayconfig_rotation) value specifying the requested screen orientation for this path.

### -field RefreshRate

A [**DISPLAYCONFIG_RATIONAL**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_rational) structure containing the requested refresh rate for this path. **RefreshRate** must match a refresh rate supported by the driver for the specified resolution.

> [!NOTE]
> This refresh rate is defined as progressive as remote drivers can only support progressive target modes.

### -field VSyncFreqDivider

The V Sync divider value for the specified **RefreshRate**.

### -field MonitorScaleFactor

The requested monitor DPI for this path. Note that this value is just a hint and OS may override the value to ensure the DPI configuration of the session is valid. Valid values are 100 to 500 inclusive.

### -field PhysicalWidthOverride

Physical width override for the specified monitor, in millimeters. A value of zero means no override.

### -field PhysicalHeightOverride

Physical height override for the specified monitor, in millimeters. A value of zero means no override.

## -remarks

An indirect display driver (IDD) calls [**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md) when it receives a new display configuration. It passes an array of **IDDCX_DISPLAYCONFIGPATH** structures in [**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE**](ns-iddcx-idarg_in_adapterdisplayconfigupdate.md).

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE**](ns-iddcx-idarg_in_adapterdisplayconfigupdate.md)

[**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md)
