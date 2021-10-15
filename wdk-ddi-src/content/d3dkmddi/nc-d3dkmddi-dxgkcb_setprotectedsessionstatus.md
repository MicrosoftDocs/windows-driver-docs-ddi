---
UID: NC:d3dkmddi.DXGKCB_SETPROTECTEDSESSIONSTATUS
tech.root: display
title: DXGKCB_SETPROTECTEDSESSIONSTATUS
ms.date: 10/13/2021
targetos: Windows
description: Learn more about the DXGKCB_SETPROTECTEDSESSIONSTATUS callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1709 (WDDM 2.3)
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
 - d3dkmddi.h
api_name:
 - DXGKCB_SETPROTECTEDSESSIONSTATUS
f1_keywords:
 - DXGKCB_SETPROTECTEDSESSIONSTATUS
 - d3dkmddi/DXGKCB_SETPROTECTEDSESSIONSTATUS
dev_langs:
 - c++
---

## -description

A kernel-mode display miniport driver calls **DXGKCB_SETPROTECTEDSESSIONSTATUS** to set the status of a protected session.

## -parameters

### -param pProtectedSessionStatus

[in] Pointer to a [**DXGKARGCB_PROTECTEDSESSIONSTATUS**](ns-d3dkmddi-_dxgkargcb_protectedsessionstatus.md) structure that identifies the protected session and its status.

## -returns

**DXGKCB_SETPROTECTEDSESSIONSTATUS** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_PROTECTEDSESSIONSTATUS**](ns-d3dkmddi-_dxgkargcb_protectedsessionstatus.md) and call **DxgkCbSetProtectedSessionStatus** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_PROTECTEDSESSIONSTATUS**](ns-d3dkmddi-_dxgkargcb_protectedsessionstatus.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
