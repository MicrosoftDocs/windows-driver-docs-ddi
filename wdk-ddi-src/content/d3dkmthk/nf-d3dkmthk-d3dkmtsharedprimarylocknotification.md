---
UID: NF:d3dkmthk.D3DKMTSharedPrimaryLockNotification
title: D3DKMTSharedPrimaryLockNotification function (d3dkmthk.h)
description: The D3DKMTSharedPrimaryLockNotification function notifies the operating system about an upcoming lock to a shared primary surface.
old-location: display\d3dkmtsharedprimarylocknotification.htm
ms.date: 03/02/2022
keywords: ["D3DKMTSharedPrimaryLockNotification function"]
ms.keywords: D3DKMTSharedPrimaryLockNotification, D3DKMTSharedPrimaryLockNotification function [Display Devices], OpenGL_Functions_a6696797-0a53-4687-8a70-4878b550fa03.xml, d3dkmthk/D3DKMTSharedPrimaryLockNotification, display.d3dkmtsharedprimarylocknotification
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
 - D3DKMTSharedPrimaryLockNotification
 - d3dkmthk/D3DKMTSharedPrimaryLockNotification
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
 - D3DKMTSharedPrimaryLockNotification
---

# D3DKMTSharedPrimaryLockNotification function

## -description

The **D3DKMTSharedPrimaryLockNotification** function notifies the operating system about an upcoming lock to a shared primary surface.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md) structure that describes the shared primary surface that an application will lock.

## -returns

**D3DKMTSharedPrimaryLockNotification** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | Notification about an upcoming lock to a shared primary surface was successfully performed. |
| STATUS_NO_MEMORY | **D3DKMTSharedPrimaryLockNotification** could not complete because of insufficient memory. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values that are defined in Ntstatus.h.

## -remarks

The OpenGL ICD calls the **D3DKMTSharedPrimaryLockNotification** function to inform the operating system that an application is about to lock the GDI shared primary surface that exists on the graphics adapter and video present source that the *AdapterLuid* and *VidPnSourceId* members of the [D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md) structure specify. The OpenGL ICD must call **D3DKMTSharedPrimaryLockNotification** before it calls the [D3DKMTLock](nf-d3dkmthk-d3dkmtlock.md) function for the GDI shared primary surface to ensure that the operating system disables all sprites that intersect with the lock region that the *LockRect* member of [D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md) specifies.

## -see-also

[D3DKMTLock](nf-d3dkmthk-d3dkmtlock.md)

[D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md)
