---
UID: NS:d3dkmthk._D3DKMT_RELEASEKEYEDMUTEX
title: "_D3DKMT_RELEASEKEYEDMUTEX"
author: windows-driver-content
description: The D3DKMT_RELEASEKEYEDMUTEX structure describes a keyed mutex that the D3DKMTReleaseKeyedMutex function releases.
old-location: display\d3dkmt_releasekeyedmutex.htm
old-project: display
ms.assetid: 0ba40b4e-2e1d-45fa-9222-e162a39eea33
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_RELEASEKEYEDMUTEX, D3DKMT_RELEASEKEYEDMUTEX structure [Display Devices], OpenGL_Structs_6f167c25-afb8-4ddc-9441-be713bba78f4.xml, _D3DKMT_RELEASEKEYEDMUTEX, d3dkmthk/D3DKMT_RELEASEKEYEDMUTEX, display.d3dkmt_releasekeyedmutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_RELEASEKEYEDMUTEX is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_RELEASEKEYEDMUTEX
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_RELEASEKEYEDMUTEX
---

# _D3DKMT_RELEASEKEYEDMUTEX structure


## -description


The D3DKMT_RELEASEKEYEDMUTEX structure describes a keyed mutex that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547129">D3DKMTReleaseKeyedMutex</a> function releases. 


## -struct-fields




### -field hKeyedMutex

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object to release. 


### -field Key

[in] A 64-bit value that specifies the key value to release the mutex to. 


### -field FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547129">D3DKMTReleaseKeyedMutex</a>
 

 

