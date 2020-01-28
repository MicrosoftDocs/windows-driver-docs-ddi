---
UID: NC:d3dkmthk.PFND3DKMT_SETSTEREOENABLED
title: PFND3DKMT_SETSTEREOENABLED (d3dkmthk.h)
description: The PFND3DKMT_SETSTEREOENABLED callback function sets stereo enabled.
ms.assetid: ee87c614-07b4-47a3-a6f5-afb2fdae9772
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETSTEREOENABLED"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver:
req.umdf-ver:
req.lib: Gdi32.lib
req.dll: Gdi32.dll
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
- DllExport
api_location: 
- GDI32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name: 
- PFND3DKMT_SETSTEREOENABLED
- D3DKMTSetStereoEnabled
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SETSTEREOENABLED callback function

## -description

The PFND3DKMT_SETSTEREOENABLED callback function retrieves a Boolean value that indicates whether the operating system's stereoscopic 3-D display behavior is enabled.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETSTEREOENABLED D3DKMTSetStereoEnabled; 

// Definition

_Check_return_ NTSTATUS APIENTRY D3DKMTSetStereoEnabled(
  _In_ BOOL bStereoEnabled
);

```

## -parameters

### -param Arg1: 

*\_In\_* *bStereoEnabled*

**TRUE** if the operating system's stereoscopic 3-D display behavior is enabled; **FALSE** otherwise.

## -returns

Returns STATUS_SUCCESS if the function completed successfully.

This function might also return other NTSTATUS values.

## -remarks




## -see-also
