---
UID: NS:d3dkmthk._D3DKMT_OUTPUTDUPL_RELEASE_FRAME
title: _D3DKMT_OUTPUTDUPL_RELEASE_FRAME
author: windows-driver-content
description: Defines the duplicated desktop image that is to be released in a call to the D3DKMTOutputDuplReleaseFrame function.
old-location: display\d3dkmt_outputdupl_release_frame.htm
old-project: display
ms.assetid: 98d31b6b-c31a-4509-a89f-f09932468313
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmt_outputdupl_release_frame, _D3DKMT_OUTPUTDUPL_RELEASE_FRAME, D3DKMT_OUTPUTDUPL_RELEASE_FRAME, d3dkmthk/D3DKMT_OUTPUTDUPL_RELEASE_FRAME, D3DKMT_OUTPUTDUPL_RELEASE_FRAME structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
apiname: 
-	D3DKMT_OUTPUTDUPL_RELEASE_FRAME
product: Windows
targetos: Windows
req.typenames: D3DKMT_OUTPUTDUPL_RELEASE_FRAME
---

# _D3DKMT_OUTPUTDUPL_RELEASE_FRAME structure


## -description


Defines the duplicated desktop image that is to be released in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtoutputduplreleaseframe.md">D3DKMTOutputDuplReleaseFrame</a> function.


## -syntax


````
typedef struct _D3DKMT_OUTPUTDUPL_RELEASE_FRAME {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_OUTPUTDUPL_RELEASE_FRAME;
````


## -struct-fields




### -field hAdapter

[in] A handle of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the graphics adapter that contains the duplicated desktop image.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology.


### -field NextKeyMutexIdx

 



## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtoutputduplreleaseframe.md">D3DKMTOutputDuplReleaseFrame</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OUTPUTDUPL_RELEASE_FRAME structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

