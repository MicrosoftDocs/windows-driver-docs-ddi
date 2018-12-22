---
UID: NS:d3dkmthk._D3DKMT_CREATEPROTECTEDSESSION
title: "_D3DKMT_CREATEPROTECTEDSESSION"
description: Used to create a protected session.
old-location: display\d3dkmt-createprotectedsession.htm
ms.assetid: 4ec42f5a-df33-4da3-a959-64cb400f3177
ms.date: 05/10/2018
ms.keywords: D3DKMT_CREATEPROTECTEDSESSION, D3DKMT_CREATEPROTECTEDSESSION structure [Display Devices], _D3DKMT_CREATEPROTECTEDSESSION, d3dkmthk/D3DKMT_CREATEPROTECTEDSESSION, display.d3dkmt-createprotectedsession
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CREATEPROTECTEDSESSION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEPROTECTEDSESSION
---

# _D3DKMT_CREATEPROTECTEDSESSION structure


## -description


Used to create a protected session.


## -struct-fields




### -field hDevice

A handle for the device.


### -field hSyncObject

A monitored fence handle associated with the session.


### -field pPrivateDriverData

Private driver data.


### -field PrivateDriverDataSize

Size of private driver data.


### -field pPrivateRuntimeData

Private runtime data.


### -field PrivateRuntimeDataSize

Size of private runtime data.


### -field hHandle

The protected session handle.

