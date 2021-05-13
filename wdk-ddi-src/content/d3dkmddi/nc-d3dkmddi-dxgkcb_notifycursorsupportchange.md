---
UID: NC:d3dkmddi.DXGKCB_NOTIFYCURSORSUPPORTCHANGE
tech.root: display
title: DXGKCB_NOTIFYCURSORSUPPORTCHANGE
ms.date: 05/13/2021
targetos: Windows
description: The DxgkCbNotifyCursorSupportChange callback function is called by the kernel-mode driver to notify the OS that cursor support has been changed.
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
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
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
 - DXGKCB_NOTIFYCURSORSUPPORTCHANGE
f1_keywords:
 - DXGKCB_NOTIFYCURSORSUPPORTCHANGE
 - d3dkmddi/DXGKCB_NOTIFYCURSORSUPPORTCHANGE
dev_langs:
 - c++
---

## -description

The **DxgkCbNotifyCursorSupportChange** callback function is called by the kernel-mode driver to notify the operating system that cursor support has been changed.

## -parameters

### -param pArgs

[in] Pointer to a [**DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE**](ns-d3dkmddi-dxgkargcb_notifycursorsupportchange.md) structure that contains the arguments for this callback.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS error code.

## -remarks

The kernel-mode driver can call **DxgkCbNotifyCursorSupportChange** either inside a DDI call from the OS or in an arbitrary thread before the adapter is stopped/removed.

Available in WDDM 2.8 and later versions.

## -see-also

[**DXGKARGCB_NOTIFYCURSORSUPPORTCHANGE**](ns-d3dkmddi-dxgkargcb_notifycursorsupportchange.md)
