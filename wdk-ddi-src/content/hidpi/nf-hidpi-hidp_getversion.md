---
UID: NF:hidpi.HidP_GetVersion
tech.root: hid
title: HidP_GetVersion
ms.date: 11/18/2021
targetos: Windows
description: The HidP_GetVersion function is a header-only implementation that returns the HID API version.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidpi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - hidpi.h
api_name:
 - HidP_GetVersion
f1_keywords:
 - HidP_GetVersion
 - hidpi/HidP_GetVersion
dev_langs:
 - c++
---

## -description

The **HidP_GetVersion** function is a header-only implementation that returns the HID API version.

## -parameters

### -param Version [out]

The version of the HID API.

## -returns

**HidP_GetVersion** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

Call **HidP_GetVersion** at runtime before using [HidP_GetButtonArray](nf-hidpi-hidp_getbuttonarray.md) or [HidP_SetButtonArray](nf-hidpi-hidp_setbuttonarray.md). The **HidP_GetButtonArray** and **HidP_SetButtonArray** functions are only available on operating systems where **HidP_GetVersion** returns a value of two or greater. Version two of the API corresponds to Windows 11.

**HidP_GetVersion** is safe to call on down-level systems because it is a header-only implementation.

## -see-also

- [HidP_GetButtonArray](nf-hidpi-hidp_getbuttonarray.md)
- [HidP_SetButtonArray](nf-hidpi-hidp_setbuttonarray.md)
