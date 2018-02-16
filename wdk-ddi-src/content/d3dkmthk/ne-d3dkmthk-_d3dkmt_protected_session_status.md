---
UID: NE:d3dkmthk._D3DKMT_PROTECTED_SESSION_STATUS
title: "_D3DKMT_PROTECTED_SESSION_STATUS"
author: windows-driver-content
description: Indicates the status of the protected session.
old-location: display\d3dkmt-protected-session-status.htm
old-project: display
ms.assetid: 87a7de73-5e94-4016-b760-f3501ead08ac
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMT_PROTECTED_SESSION_STATUS_OK, display.d3dkmt-protected-session-status, D3DKMT_PROTECTED_SESSION_STATUS, D3DKMT_PROTECTED_SESSION_STATUS_INVALID, D3DKMT_PROTECTED_SESSION_STATUS enumeration [Display Devices], d3dkmthk/D3DKMT_PROTECTED_SESSION_STATUS_INVALID, d3dkmthk/D3DKMT_PROTECTED_SESSION_STATUS, D3DKMT_PROTECTED_SESSION_STATUS_OK, _D3DKMT_PROTECTED_SESSION_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_PROTECTED_SESSION_STATUS
product: Windows
targetos: Windows
req.typenames: D3DKMT_PROTECTED_SESSION_STATUS
---

# _D3DKMT_PROTECTED_SESSION_STATUS enumeration


## -description


Indicates the status of the protected session.


## -syntax


````
typedef enum _D3DKMT_PROTECTED_SESSION_STATUS { 
  D3DKMT_PROTECTED_SESSION_STATUS_OK       = 0,
  D3DKMT_PROTECTED_SESSION_STATUS_INVALID  = 1
} D3DKMT_PROTECTED_SESSION_STATUS;
````


## -enum-fields




### -field D3DKMT_PROTECTED_SESSION_STATUS_OK

Indicates that the status is okay.


### -field D3DKMT_PROTECTED_SESSION_STATUS_INVALID

Indicates that the status is invalid.

