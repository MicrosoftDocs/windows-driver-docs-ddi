---
UID: NS:d3dkmthk._D3DKMT_DEVICE_ESCAPE
title: "_D3DKMT_DEVICE_ESCAPE"
author: windows-driver-content
description: Do not use the D3DKMT_DEVICE_ESCAPE structure or D3DKMT_DEVICEESCAPE_TYPE enumeration. They are for testing purposes only. The D3DKMT_DEVICE_ESCAPE structure describes how to control the display device in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_device_escape.htm
old-project: display
ms.assetid: 274bdd80-e898-42c7-8adc-8eae4e895b5f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.d3dkmt_device_escape, _D3DKMT_DEVICE_ESCAPE, OpenGL_Structs_38febe04-ae75-475a-ab69-81995acb567b.xml, D3DKMT_DEVICE_ESCAPE, d3dkmthk/D3DKMT_DEVICE_ESCAPE, D3DKMT_DEVICE_ESCAPE structure [Display Devices]
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
-	D3DKMT_DEVICE_ESCAPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEVICE_ESCAPE
---

# _D3DKMT_DEVICE_ESCAPE structure


## -description



   Do not use the D3DKMT_DEVICE_ESCAPE structure or D3DKMT_DEVICEESCAPE_TYPE enumeration. They are for testing purposes only.
   

The D3DKMT_DEVICE_ESCAPE structure describes how to control the display device in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a> function.


## -syntax


````
typedef struct _D3DKMT_DEVICE_ESCAPE {
  D3DKMT_DEVICEESCAPE_TYPE Type;
  union {
    struct {
      D3DKMT_HANDLE                  hPrimaryAllocation;
      D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
    } VidPnFromAllocation;
  };
} D3DKMT_DEVICE_ESCAPE;
````


## -struct-fields




### -field Type


### -field VidPnFromAllocation


### -field VidPnFromAllocation.hPrimaryAllocation

[in] The primary allocation handle.


### -field VidPnFromAllocation.VidPnSourceId

[out] The VidPN source ID of the primary allocation.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtescape.md">D3DKMTEscape</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_escape.md">D3DKMT_ESCAPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DEVICE_ESCAPE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

