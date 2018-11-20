---
UID: NC:d3dkmthk.PFND3DKMT_OPENADAPTERFROMDEVICENAME
title: PFND3DKMT_OPENADAPTERFROMDEVICENAME
author: windows-driver-content
description: Pfnd3dkmtOpenadapterfromdevicename maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
ms.assetid: 30832e65-d6bd-4d48-bd57-1b29620b47fe
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_OPENADAPTERFROMDEVICENAME
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# PFND3DKMT_OPENADAPTERFROMDEVICENAME callback function

## -description

Pfnd3dkmtOpenadapterfromdevicename maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENADAPTERFROMDEVICENAME Pfnd3dkmtOpenadapterfromdevicename; 

// Definition

NTSTATUS Pfnd3dkmtOpenadapterfromdevicename 
(
	D3DKMT_OPENADAPTERFROMDEVICENAME *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENADAPTERFROMDEVICENAME](ns-d3dkmthk-_d3dkmt_openadapterfromdevicename.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
