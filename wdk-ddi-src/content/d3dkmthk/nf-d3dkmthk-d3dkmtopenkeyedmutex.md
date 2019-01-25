---
UID: NF:d3dkmthk.D3DKMTOpenKeyedMutex
title: D3DKMTOpenKeyedMutex function (d3dkmthk.h)
description: The D3DKMTOpenKeyedMutex function opens a keyed mutex object.
old-location: display\d3dkmtopenkeyedmutex.htm
ms.assetid: 309a43bf-5fad-409f-83e6-e88361b03827
ms.date: 05/10/2018
ms.keywords: D3DKMTOpenKeyedMutex, D3DKMTOpenKeyedMutex function [Display Devices], OpenGL_Functions_6e2179a9-932f-4bd3-b222-4d5f1471636c.xml, d3dkmthk/D3DKMTOpenKeyedMutex, display.d3dkmtopenkeyedmutex
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTOpenKeyedMutex is supported beginning with the Windows 7 operating system.
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTOpenKeyedMutex
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOpenKeyedMutex function

## -description

The <b>D3DKMTOpenKeyedMutex</b> function opens a keyed mutex object.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548135">D3DKMT_OPENKEYEDMUTEX</a> structure that describes a keyed mutex object.

## -returns

D3DKMTOpenKeyedMutex returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully opened. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTOpenKeyedMutex](https://msdn.microsoft.com/library/windows/hardware/ff547054)  could not complete because of insufficient memory. | 

This function might also return other NTSTATUS values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548135">D3DKMT_OPENKEYEDMUTEX</a>
 

 

