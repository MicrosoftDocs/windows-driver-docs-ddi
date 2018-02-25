---
UID: NS:d3dkmddi._DXGKARGCB_PROTECTEDSESSIONSTATUS
title: "_DXGKARGCB_PROTECTEDSESSIONSTATUS"
author: windows-driver-content
description: Used for information on the status of the protected session.
old-location: display\dxgkargcb_protectedsessionstatus.htm
old-project: display
ms.assetid: 417480C5-8B24-4504-8B2D-DB9D38E4C11B
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, B, C, D, DXGKARGCB_PROTECTEDSESSIONSTATUS, DXGKARGCB_PROTECTEDSESSIONSTATUS structure [Display Devices], E, G, I, K, N, O, P, R, S, T, U, X, _, _DXGKARGCB_PROTECTEDSESSIONSTATUS, d3dkmddi/DXGKARGCB_PROTECTEDSESSIONSTATUS, display.dxgkargcb_protectedsessionstatus"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARGCB_PROTECTEDSESSIONSTATUS
product: Windows
targetos: Windows
req.typenames: DXGKARGCB_PROTECTEDSESSIONSTATUS
---

# _DXGKARGCB_PROTECTEDSESSIONSTATUS structure


## -description


Used for information on the status of the protected session.


## -syntax


````
typedef struct _DXGKARGCB_PROTECTEDSESSIONSTATUS {
  HANDLE                        hProtectedSession;
  DXGK_PROTECTED_SESSION_STATUS Status;
} DXGKARGCB_PROTECTEDSESSIONSTATUS;
````


## -struct-fields




### -field hProtectedSession

A handle for the protected session that was passed to DxgkDdiCreateProtectedSession.


### -field Status

The status of the protected session

