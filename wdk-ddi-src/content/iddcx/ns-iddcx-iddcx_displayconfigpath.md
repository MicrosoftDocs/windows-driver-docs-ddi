---
UID: NS:iddcx.IDDCX_DISPLAYCONFIGPATH
title: IDDCX_DISPLAYCONFIGPATH
author: windows-driver-content
description: The display monitor configuration path.
tech.root: display
ms.assetid: 5dce6205-f03c-4ca5-8f40-09a24eacbd13
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
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
targetos: Windows
---

# IDDCX_DISPLAYCONFIGPATH structure

## -description

The display monitor configuration path.

## -struct-fields

### -field Size

Total size of the structure.

### -field MonitorObject

The handle the driver provides to identify the monitor this path is targeted at.

### -field Position

Requested desktop position for this path.

### -field Resolution

Desktop resolution for this path. Must match a resolution supported by the driver.

### -field Rotation

Requested orientation for this path.

### -field RefreshRate

Requested refresh rate for this path. Must match a refresh rate supported by the driver for this resolution

> [!NOTE]
> This refresh rate is defined as progressive as remote drivers can only support progressive target modes.

### -field VSyncFreqDivider

The V Sync divider value for the specified *RefreshRate*.

### -field MonitorScaleFactor

Requested monitor DPI for this path. Note that this value is just a hint and OS may override the value to ensure the DPI configuration of the session is valid.

Valid values are 100 to 500 inclusive.

### -field PhysicalWidthOverride

Physical width override for the specified monitor in millimeters, zero means no override.

### -field PhysicalHeightOverride

Physical height override for the specified monitor in millimeters, zero means no override.

## -remarks

## -see-also