---
UID: NC:d3dkmthk.PFND3DKMT_RELEASEPROCESSVIDPNSOURCEOWNERS
title: PFND3DKMT_RELEASEPROCESSVIDPNSOURCEOWNERS (d3dkmthk.h)
description: The PFND3DKMT_RELEASEPROCESSVIDPNSOURCEOWNERS callback function releases the video present network source owners for a process.
ms.assetid: e4a406fc-dd63-4fb9-a783-96fa483c92af
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_RELEASEPROCESSVIDPNSOURCEOWNERS"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_RELEASEPROCESSVIDPNSOURCEOWNERS
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_RELEASEPROCESSVIDPNSOURCEOWNERS callback function

## -description

The PFND3DKMT_RELEASEPROCESSVIDPNSOURCEOWNERS callback function releases the video present network source owners for a process.

## -prototype

```cpp
//Declaration

PFND3DKMT_RELEASEPROCESSVIDPNSOURCEOWNERS Pfnd3dkmtReleaseprocessvidpnsourceowners; 

// Definition

NTSTATUS Pfnd3dkmtReleaseprocessvidpnsourceowners 
(
	HANDLE Arg1
)
{...}

```

## -parameters

### -param Arg1

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
