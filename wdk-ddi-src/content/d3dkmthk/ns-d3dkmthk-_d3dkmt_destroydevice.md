---
UID: NS:d3dkmthk._D3DKMT_DESTROYDEVICE
title: "_D3DKMT_DESTROYDEVICE"
author: windows-driver-content
description: The D3DKMT_DESTROYDEVICE structure contains a handle to the kernel-mode device context to release.
old-location: display\d3dkmt_destroydevice.htm
old-project: display
ms.assetid: f74ea9da-71ba-466a-b102-78d999d38096
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_DESTROYDEVICE, D3DKMT_DESTROYDEVICE, d3dkmthk/D3DKMT_DESTROYDEVICE, OpenGL_Structs_dc051065-8102-453f-81cd-aa39ee592926.xml, D3DKMT_DESTROYDEVICE structure [Display Devices], display.d3dkmt_destroydevice"
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
-	D3DKMT_DESTROYDEVICE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYDEVICE
---

# _D3DKMT_DESTROYDEVICE structure


## -description


The D3DKMT_DESTROYDEVICE structure contains a handle to the kernel-mode device context to release.


## -syntax


````
typedef struct _D3DKMT_DESTROYDEVICE {
  D3DKMT_HANDLE hDevice;
} D3DKMT_DESTROYDEVICE;
````


## -struct-fields




### -field hDevice

[in] A handle to the device context that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) supplied and that is returned from the call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> function.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroydevice.md">D3DKMTDestroyDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DESTROYDEVICE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

