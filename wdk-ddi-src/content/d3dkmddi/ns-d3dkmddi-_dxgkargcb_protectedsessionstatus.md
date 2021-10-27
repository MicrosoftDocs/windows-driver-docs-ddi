---
UID: NS:d3dkmddi._DXGKARGCB_PROTECTEDSESSIONSTATUS
title: DXGKARGCB_PROTECTEDSESSIONSTATUS (d3dkmddi.h)
description: Used for information on the status of the protected session.
old-location: display\dxgkargcb_protectedsessionstatus.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_PROTECTEDSESSIONSTATUS structure"]
ms.keywords: DXGKARGCB_PROTECTEDSESSIONSTATUS, DXGKARGCB_PROTECTEDSESSIONSTATUS structure [Display Devices], _DXGKARGCB_PROTECTEDSESSIONSTATUS, d3dkmddi/DXGKARGCB_PROTECTEDSESSIONSTATUS, display.dxgkargcb_protectedsessionstatus
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709 (WDDM 2.3)
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_PROTECTEDSESSIONSTATUS
f1_keywords:
 - _DXGKARGCB_PROTECTEDSESSIONSTATUS
 - d3dkmddi/_DXGKARGCB_PROTECTEDSESSIONSTATUS
 - DXGKARGCB_PROTECTEDSESSIONSTATUS
 - d3dkmddi/DXGKARGCB_PROTECTEDSESSIONSTATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_PROTECTEDSESSIONSTATUS
 - DXGKARGCB_PROTECTEDSESSIONSTATUS
---

# DXGKARGCB_PROTECTEDSESSIONSTATUS structure

## -description

The **DXGKARGCB_PROTECTEDSESSIONSTATUS** structure contains arguments used by the [**DXGKCB_SETPROTECTEDSESSIONSTATUS**](nc-d3dkmddi-dxgkcb_setprotectedsessionstatus.md) callback function, to set the status on a protected session.

## -struct-fields

### -field hProtectedSession [in]

A handle for the protected session that was passed to [**DxgkDdiCreateProtectedSession**](nc-d3dkmddi-dxgkddi_createprotectedsession.md).

### -field Status [in]

A [**DXGK_PROTECTED_SESSION_STATUS**](ne-d3dkmddi-_dxgk_protected_session_status.md) value that indicates the status of the protected session.

## -see-also

[**DXGK_PROTECTED_SESSION_STATUS**](ne-d3dkmddi-_dxgk_protected_session_status.md)

[**DXGKCB_SETPROTECTEDSESSIONSTATUS**](nc-d3dkmddi-dxgkcb_setprotectedsessionstatus.md)

[**DxgkDdiCreateProtectedSession**](nc-d3dkmddi-dxgkddi_createprotectedsession.md)
