---
UID: NS:d3dkmthk._D3DKMT_CHECKMONITORPOWERSTATE
title: "_D3DKMT_CHECKMONITORPOWERSTATE"
author: windows-driver-content
description: The D3DKMT_CHECKMONITORPOWERSTATE structure describes the connection to the monitor for which to check the power state.
old-location: display\d3dkmt_checkmonitorpowerstate.htm
old-project: display
ms.assetid: aa7cee9a-5051-4ebc-be7c-ac9ac91ba631
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: OpenGL_Structs_2c4ec2cb-c35a-4447-8e35-dc8e4964e8b2.xml, _D3DKMT_CHECKMONITORPOWERSTATE, d3dkmthk/D3DKMT_CHECKMONITORPOWERSTATE, D3DKMT_CHECKMONITORPOWERSTATE, display.d3dkmt_checkmonitorpowerstate, D3DKMT_CHECKMONITORPOWERSTATE structure [Display Devices]
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
-	D3DKMT_CHECKMONITORPOWERSTATE
product: Windows
targetos: Windows
req.typenames: D3DKMT_CHECKMONITORPOWERSTATE
---

# _D3DKMT_CHECKMONITORPOWERSTATE structure


## -description


The D3DKMT_CHECKMONITORPOWERSTATE structure describes the connection to the monitor for which to check the power state. 


## -syntax


````
typedef struct _D3DKMT_CHECKMONITORPOWERSTATE {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_CHECKMONITORPOWERSTATE;
````


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcheckmonitorpowerstate.md">D3DKMTCheckMonitorPowerState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CHECKMONITORPOWERSTATE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

