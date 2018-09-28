---
UID: NC:d3dkmthk.PFND3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION
title: PFND3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION
author: windows-driver-content
description: The PFND3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION callback function notifies the operating system that a shared primary surface was unlocked.
ms.assetid: c6a4be3f-33b5-4369-8b27-06561bf43873
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION callback function

## -description

The PFND3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION callback function notifies the operating system that a shared primary surface was unlocked.

## -prototype

```
//Declaration

PFND3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION Pfnd3dkmtSharedprimaryunlocknotification; 

// Definition

NTSTATUS Pfnd3dkmtSharedprimaryunlocknotification 
(
	const D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimaryunlocknotification.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also