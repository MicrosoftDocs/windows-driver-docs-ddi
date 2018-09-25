---
UID: NS:d3dkmthk._D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
title: "_D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE"
author: windows-driver-content
description: Used to query information on the protected session.
old-location: display\d3dkmt-queryprotectedsessioninfofromnthandle.htm
ms.assetid: e08d27e7-e9b7-45e7-9bbd-dcb9aa8f85ed
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE, D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE structure [Display Devices], _D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE, d3dkmthk/D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE, display.d3dkmt-queryprotectedsessioninfofromnthandle
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE
---

# _D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE structure


## -description


Used to query information on the protected session.


## -struct-fields




### -field hNtHandle

The protected NT session handle.


### -field pPrivateDriverData

The private driver data.


### -field PrivateDriverDataSize

The size of the private driver data.


### -field pPrivateRuntimeData

The private runtime data.


### -field PrivateRuntimeDataSize

The size of the private runtime data.

