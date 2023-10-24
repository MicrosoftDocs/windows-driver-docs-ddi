---
UID: NE:iddcx.IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE
tech.root: display
title: IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE
f1_keywords:
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE
 - iddcx/IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE
---

## -description

A **IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE** enumeration value specifies the color mode to be set on a monitor.

## -enum-fields

### -field IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE_UNINITIALIZED:0

Indicates that an **IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE** variable has not yet been assigned a meaningful value.

### -field IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE_SDR:1

Allows a driver to indicate that it wants to run in SDR mode even if the OS may wish to use HDR or SDR WCG.

### -field IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE_SDRWCG:2

Allows a driver to indicate that it wants to run in SDR WCG mode even if the OS may wish to use HDR or SDR.

### -field IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE_HDR10:3

Allows a driver to indicate that it wants to run in HDR mode even if the OS may wish to use SDR or SDR WCG.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md)

[**IDDCX_DISPLAYCONFIG_MODE**](ns-iddcx-iddcx_displayconfig_mode.md)

[**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md)

[**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md)
