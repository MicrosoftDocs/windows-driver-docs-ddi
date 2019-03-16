---
UID: NF:d3dkmthk.D3DKMTCreateOverlay
title: D3DKMTCreateOverlay function (d3dkmthk.h)
description: The D3DKMTCreateOverlay function creates a kernel-mode overlay object.
old-location: display\d3dkmtcreateoverlay.htm
ms.assetid: f77c20a1-c05c-456b-874b-e07d6edf5982
ms.date: 05/10/2018
ms.keywords: D3DKMTCreateOverlay, D3DKMTCreateOverlay function [Display Devices], OpenGL_Functions_3848b4de-9ed0-4e4f-87aa-677bdbbaa7e0.xml, d3dkmthk/D3DKMTCreateOverlay, display.d3dkmtcreateoverlay
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- D3DKMTCreateOverlay
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCreateOverlay function

## -description

The <b>D3DKMTCreateOverlay</b> function creates a kernel-mode overlay object.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547840">D3DKMT_CREATEOVERLAY</a> structure that describes overlay hardware.

## -returns

<b>D3DKMTCreateOverlay</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The kernel-mode overlay object was successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateOverlay](https://msdn.microsoft.com/library/windows/hardware/ff546852)  could not complete because of insufficient memory. | 

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547840">D3DKMT_CREATEOVERLAY</a>
