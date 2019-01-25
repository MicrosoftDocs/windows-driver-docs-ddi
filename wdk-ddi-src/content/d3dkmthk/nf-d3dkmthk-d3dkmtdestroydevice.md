---
UID: NF:d3dkmthk.D3DKMTDestroyDevice
title: D3DKMTDestroyDevice function (d3dkmthk.h)
description: The D3DKMTDestroyDevice function releases a kernel-mode device context.
old-location: display\d3dkmtdestroydevice.htm
ms.assetid: 7699214a-0cd2-401a-9f66-199d181abce4
ms.date: 05/10/2018
ms.keywords: D3DKMTDestroyDevice, D3DKMTDestroyDevice function [Display Devices], OpenGL_Functions_66b283a1-deee-4a49-a02d-217567d35873.xml, d3dkmthk/D3DKMTDestroyDevice, display.d3dkmtdestroydevice
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
-	D3DKMTDestroyDevice
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTDestroyDevice function


## -description


The <b>D3DKMTDestroyDevice</b> function releases a kernel-mode device context.


## -parameters




### -param D3DKMT_DESTROYDEVICE

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547881">D3DKMT_DESTROYDEVICE</a> structure that contains the handle to the kernel-mode device context.

## -returns

<b>D3DKMTDestroyDevice</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully released.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547881">D3DKMT_DESTROYDEVICE</a>
 
