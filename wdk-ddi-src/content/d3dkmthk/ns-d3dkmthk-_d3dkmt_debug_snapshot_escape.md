---
UID: NS:d3dkmthk._D3DKMT_DEBUG_SNAPSHOT_ESCAPE
title: "_D3DKMT_DEBUG_SNAPSHOT_ESCAPE"
author: windows-driver-content
description: Do not use the D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure; it is for testing purposes only. The D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure describes a debug snapshot that is returned in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_debug_snapshot_escape.htm
ms.assetid: f5aa4829-6264-444c-b8e6-23854cb87534
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMT_DEBUG_SNAPSHOT_ESCAPE, D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure [Display Devices], OpenGL_Structs_c8ece404-4d73-4d77-96c3-b2f5ceb94feb.xml, _D3DKMT_DEBUG_SNAPSHOT_ESCAPE, d3dkmthk/D3DKMT_DEBUG_SNAPSHOT_ESCAPE, display.d3dkmt_debug_snapshot_escape
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
-	D3DKMT_DEBUG_SNAPSHOT_ESCAPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DEBUG_SNAPSHOT_ESCAPE
---

# _D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure


## -description



   Do not use the D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure; it is for testing purposes only.
   

The D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure describes a debug snapshot that is returned in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> function.


## -struct-fields




### -field Length

[out] The actual length of the snapshot written in the <b>Buffer</b> member.


### -field Buffer

[out] The buffer to place the snapshot in.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547970">D3DKMT_ESCAPE</a>
 

 

