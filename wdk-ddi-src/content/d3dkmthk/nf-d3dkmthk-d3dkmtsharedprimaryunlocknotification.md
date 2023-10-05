---
UID: NF:d3dkmthk.D3DKMTSharedPrimaryUnLockNotification
title: D3DKMTSharedPrimaryUnLockNotification function (d3dkmthk.h)
description: The D3DKMTSharedPrimaryUnLockNotification function notifies the operating system that a shared primary surface was unlocked.
old-location: display\d3dkmtsharedprimaryunlocknotification.htm
ms.date: 03/02/2022
keywords: ["D3DKMTSharedPrimaryUnLockNotification function"]
ms.keywords: D3DKMTSharedPrimaryUnLockNotification, D3DKMTSharedPrimaryUnLockNotification function [Display Devices], OpenGL_Functions_311a1879-e3f7-44e2-aa1a-0c070e45bf85.xml, d3dkmthk/D3DKMTSharedPrimaryUnLockNotification, display.d3dkmtsharedprimaryunlocknotification
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTSharedPrimaryUnLockNotification
 - d3dkmthk/D3DKMTSharedPrimaryUnLockNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTSharedPrimaryUnLockNotification
---

# D3DKMTSharedPrimaryUnLockNotification function

## -description

The **D3DKMTSharedPrimaryUnLockNotification** function notifies the operating system that a shared primary surface was unlocked.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimaryunlocknotification.md) structure that describes the shared primary surface that was unlocked.

## -returns

**D3DKMTSharedPrimaryUnLockNotification** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | Notification about unlocking a shared primary surface was successfully performed. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -remarks

The OpenGL ICD calls the **D3DKMTSharedPrimaryUnLockNotification** function to inform the operating system that an application just unlocked the GDI shared primary surface that exists on the graphics adapter and video present source that the *AdapterLuid* and *VidPnSourceId* members of the [D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimaryunlocknotification.md) structure specify. The OpenGL ICD should call **D3DKMTSharedPrimaryUnLockNotification** after it calls the [D3DKMTUnlock](nf-d3dkmthk-d3dkmtunlock.md) function to unlock the GDI shared primary surface.

## -see-also

[D3DKMTUnlock](nf-d3dkmthk-d3dkmtunlock.md)

[D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimaryunlocknotification.md)
