---
UID: NC:iddcx.PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2
tech.root: display
title: PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2
ms.date: 02/10/2025
targetos: Windows
description: Learn more about the PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
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
 - iddcx.h
api_name:
 - PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2
f1_keywords:
 - PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2
 - iddcx/PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2
dev_langs:
 - c++
helpviewer_keywords:
 - PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2
---

## -description

**PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2** is a pointer to an OS callback function that updates the display configuration for the specified adapter.

## -parameters

### -param DriverGlobals

[in] Contains system-defined per-driver data.

### -param AdapterObject

[in] The adapter object that the display configuration is associated with.

### -param pInArgs

[in] Input arguments for the display configuration update.

## -returns

**PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE2** returns an NTSTATUS value that indicates the success or failure of the display configuration update.

## -remarks

An indirect display driver (IDD) shouldn't call this function directly. IDDs should instead call [**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md).

## -see-also

[**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md)
