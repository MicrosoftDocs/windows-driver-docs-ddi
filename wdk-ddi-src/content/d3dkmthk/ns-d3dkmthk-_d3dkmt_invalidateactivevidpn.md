---
UID: NS:d3dkmthk._D3DKMT_INVALIDATEACTIVEVIDPN
title: "_D3DKMT_INVALIDATEACTIVEVIDPN"
author: windows-driver-content
description: The D3DKMT_INVALIDATEACTIVEVIDPN structure describes parameters that invalidate the active video present network (VidPN) currently in use.
old-location: display\d3dkmt_invalidateactivevidpn.htm
old-project: display
ms.assetid: 51fb1993-b9f3-436a-9a6d-7d4f9bf26083
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmt_invalidateactivevidpn, OpenGL_Structs_6610529b-39db-4fc4-981a-96a6b3bf7543.xml, _D3DKMT_INVALIDATEACTIVEVIDPN, d3dkmthk/D3DKMT_INVALIDATEACTIVEVIDPN, D3DKMT_INVALIDATEACTIVEVIDPN structure [Display Devices], D3DKMT_INVALIDATEACTIVEVIDPN
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
-	D3DKMT_INVALIDATEACTIVEVIDPN
product: Windows
targetos: Windows
req.typenames: D3DKMT_INVALIDATEACTIVEVIDPN
---

# _D3DKMT_INVALIDATEACTIVEVIDPN structure


## -description


The D3DKMT_INVALIDATEACTIVEVIDPN structure describes parameters that invalidate the active video present network (VidPN) currently in use. 


## -syntax


````
typedef struct _D3DKMT_INVALIDATEACTIVEVIDPN {
  D3DKMT_HANDLE hAdapter;
  VOID          *pPrivateDriverData;
  UINT          PrivateDriverDataSize;
} D3DKMT_INVALIDATEACTIVEVIDPN;
````


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter that the VidPN exists on.


### -field pPrivateDriverData

[in] A pointer to a buffer that contains the display mode (for example, clone-view mode) that the OpenGL installable client driver (ICD) requests for the new VidPN.


### -field PrivateDriverDataSize

[in] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtinvalidateactivevidpn.md">D3DKMTInvalidateActiveVidPn</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_INVALIDATEACTIVEVIDPN structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

