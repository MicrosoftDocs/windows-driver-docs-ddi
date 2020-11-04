---
UID: NC:iddcx.PFN_IDDCXGETVERSION
title: PFN_IDDCXGETVERSION
description: PFN_IDDCXGETVERSION is a pointer to an OS callback function that gets the IddCx (Indirect Display Driver Class eXtension) version.
ms.date: 09/28/2020
ms.topic: language-reference
tech.root: display
ms.assetid: 06986111-4609-40ca-942c-126941817e8d
targetos: Windows
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
req.target-min-winverclnt: Windows 10, version 1709
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
 - PFN_IDDCXGETVERSION
f1_keywords:
 - PFN_IDDCXGETVERSION
 - iddcx/PFN_IDDCXGETVERSION
dev_langs:
 - c++
---

# PFN_IDDCXGETVERSION callback function

## -description

**PFN_IDDCXGETVERSION** is a pointer to an OS callback function that gets the IddCx (Indirect Display Driver Class eXtension) version.

## -parameters

### -param DriverGlobals

[in] Pointer to an [**IDD_DRIVER_GLOBALS**](./ns-iddcx-idd_driver_globals.md) structure containing system-defined per-driver data.

### -param pOutArgs

[out] Pointer to an [**IDARG_OUT_GETVERSION**](ns-iddcx-idarg_out_getversion.md) structure in which the driver will return the current IddCx version.

## -returns

(NTSTATUS) **PFN_IDDCXGETVERSION** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call [**IddCxGetVersion**](nf-iddcx-iddcxgetversion.md).

## -see-also

[**IDARG_OUT_GETVERSION**](ns-iddcx-idarg_out_getversion.md)

[*IddCxGetVersion**](nf-iddcx-iddcxgetversion.md)