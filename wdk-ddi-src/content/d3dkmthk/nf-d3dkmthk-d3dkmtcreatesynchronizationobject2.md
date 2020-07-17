---
UID: NF:d3dkmthk.D3DKMTCreateSynchronizationObject2
title: D3DKMTCreateSynchronizationObject2 function (d3dkmthk.h)
description: The D3DKMTCreateSynchronizationObject2 function creates a kernel-mode synchronization object.
old-location: display\d3dkmtcreatesynchronizationobject2.htm
ms.assetid: 45849844-a466-4e62-957a-bfe33a464b5a
ms.date: 05/10/2018
keywords: ["D3DKMTCreateSynchronizationObject2 function"]
ms.keywords: D3DKMTCreateSynchronizationObject2, D3DKMTCreateSynchronizationObject2 function [Display Devices], OpenGL_Functions_ba9aa4a0-19e6-40d2-8a17-d22c8756c555.xml, d3dkmthk/D3DKMTCreateSynchronizationObject2, display.d3dkmtcreatesynchronizationobject2
f1_keywords:
 - "d3dkmthk/D3DKMTCreateSynchronizationObject2"
 - "D3DKMTCreateSynchronizationObject2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCreateSynchronizationObject2 is supported beginning with the Windows 7 operating system.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTCreateSynchronizationObject2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCreateSynchronizationObject2 function

## -description

The <b>D3DKMTCreateSynchronizationObject2</b> function creates a kernel-mode synchronization object.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createsynchronizationobject2">D3DKMT_CREATESYNCHRONIZATIONOBJECT2</a> structure that describes a synchronization object.

## -returns

<b>D3DKMTCreateSynchronizationObject2</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The kernel-mode synchronization object was successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateSynchronizationObject2](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatesynchronizationobject2) could not complete because of insufficient memory. | 

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createsynchronizationobject2">D3DKMT_CREATESYNCHRONIZATIONOBJECT2</a>
 

 

