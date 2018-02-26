---
UID: NS:d3dkmthk._D3DKMT_DEBUG_SNAPSHOT_ESCAPE
title: "_D3DKMT_DEBUG_SNAPSHOT_ESCAPE"
author: windows-driver-content
description: Do not use the D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure; it is for testing purposes only. The D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure describes a debug snapshot that is returned in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_debug_snapshot_escape.htm
old-project: display
ms.assetid: f5aa4829-6264-444c-b8e6-23854cb87534
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, B, C, D, D3DKMT_DEBUG_SNAPSHOT_ESCAPE, D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure [Display Devices], E, G, H, K, M, N, O, OpenGL_Structs_c8ece404-4d73-4d77-96c3-b2f5ceb94feb.xml, P, S, T, U, _, _D3DKMT_DEBUG_SNAPSHOT_ESCAPE, d3dkmthk/D3DKMT_DEBUG_SNAPSHOT_ESCAPE, display.d3dkmt_debug_snapshot_escape"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_DEBUG_SNAPSHOT_ESCAPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEBUG_SNAPSHOT_ESCAPE
---

# _D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure


## -description



   Do not use the D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure; it is for testing purposes only.
   

The D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure describes a debug snapshot that is returned in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a> function.


## -syntax


````
typedef struct _D3DKMT_DEBUG_SNAPSHOT_ESCAPE {
  ULONG Length;
  BYTE  Buffer[1];
} D3DKMT_DEBUG_SNAPSHOT_ESCAPE;
````


## -struct-fields




### -field Length

[out] The actual length of the snapshot written in the <b>Buffer</b> member.


### -field Buffer

[out] The buffer to place the snapshot in.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_escape.md">D3DKMT_ESCAPE</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

