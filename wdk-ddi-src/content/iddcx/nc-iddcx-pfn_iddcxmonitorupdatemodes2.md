---
UID: NC:iddcx.PFN_IDDCXMONITORUPDATEMODES2
tech.root: display
title: PFN_IDDCXMONITORUPDATEMODES2
ms.date: 02/10/2025
targetos: Windows
description: Learn more about the PFN_IDDCXMONITORUPDATEMODES2 function.
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
 - PFN_IDDCXMONITORUPDATEMODES2
f1_keywords:
 - PFN_IDDCXMONITORUPDATEMODES2
 - iddcx/PFN_IDDCXMONITORUPDATEMODES2
dev_langs:
 - c++
helpviewer_keywords:
 - PFN_IDDCXMONITORUPDATEMODES2
---

## -description

**PFN_IDDCXMONITORUPDATEMODES2** is a pointer to an OS callback function that updates the mode list for a monitor.

## -parameters

### -param DriverGlobals

[in] Contains system-defined per-driver data.

### -param MonitorObject

[in] The monitor object that the mode list is associated with.

### -param pInArgs

[in] Input arguments for the function.

## -returns

**PFN_IDDCXMONITORUPDATEMODES2** returns an NTSTATUS value that indicates the success or failure of the function.

## -remarks

An indirect display driver (IDD) shouldn't use this function pointer directly. IDDs should instead call [**IddCxMonitorUpdateModes2**](nf-iddcx-iddcxmonitorupdatemodes2.md).

## -see-also

[**IddCxMonitorUpdateModes2**](nf-iddcx-iddcxmonitorupdatemodes2.md)
