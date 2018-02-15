---
UID: NS:d3dkmthk._D3DKMT_FLIPQUEUEINFO
title: "_D3DKMT_FLIPQUEUEINFO"
author: windows-driver-content
description: The D3DKMT_FLIPQUEUEINFO structure describes information about the graphics adapter's queue of flip operations that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_flipqueueinfo.htm
old-project: display
ms.assetid: 5bf5eb72-aa51-4ab3-ab68-13e6303f12a9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMT_FLIPQUEUEINFO, _D3DKMT_FLIPQUEUEINFO, display.d3dkmt_flipqueueinfo, OpenGL_Structs_db4a7b98-df53-4e1e-a990-0a2f45d71525.xml, D3DKMT_FLIPQUEUEINFO structure [Display Devices], D3DKMT_FLIPQUEUEINFO
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
-	D3DKMT_FLIPQUEUEINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_FLIPQUEUEINFO
---

# _D3DKMT_FLIPQUEUEINFO structure


## -description


The D3DKMT_FLIPQUEUEINFO structure describes information about the graphics adapter's queue of flip operations that the OpenGL installable client driver (ICD) obtains by calling the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a> function.


## -syntax


````
typedef struct _D3DKMT_FLIPQUEUEINFO {
  UINT                 MaxHardwareFlipQueueLength;
  UINT                 MaxSoftwareFlipQueueLength;
  D3DKMT_FLIPINFOFLAGS FlipFlags;
} D3DKMT_FLIPQUEUEINFO;
````


## -struct-fields




### -field MaxHardwareFlipQueueLength

[out] The maximum number of flip operations that can be queued for hardware-flip queuing.


### -field MaxSoftwareFlipQueueLength

[out] The maximum number of flip operations that can be queued for software-flip queuing  on hardware that supports memory mapped I/O (MMIO)-based flips.


### -field FlipFlags

[out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_flipinfoflags.md">D3DKMT_FLIPINFOFLAGS</a> structure that indicates, in bit-field flags, flipping capabilities.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_flipinfoflags.md">D3DKMT_FLIPINFOFLAGS</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_FLIPQUEUEINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

