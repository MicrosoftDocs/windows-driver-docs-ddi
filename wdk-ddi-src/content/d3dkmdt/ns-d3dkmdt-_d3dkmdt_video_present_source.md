---
UID: NS:d3dkmdt._D3DKMDT_VIDEO_PRESENT_SOURCE
title: "_D3DKMDT_VIDEO_PRESENT_SOURCE"
author: windows-driver-content
description: The D3DKMDT_VIDEO_PRESENT_SOURCE structure contains the unique identifier of a video present source.
old-location: display\d3dkmdt_video_present_source.htm
old-project: display
ms.assetid: 907df90c-dfea-40bf-9d08-5f5d87571ed8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMDT_VIDEO_PRESENT_SOURCE, D3DKMDT_VIDEO_PRESENT_SOURCE structure [Display Devices], DmStructs_16a61d68-9479-420e-b936-a1a0506ce8c3.xml, _D3DKMDT_VIDEO_PRESENT_SOURCE, d3dkmdt/D3DKMDT_VIDEO_PRESENT_SOURCE, display.d3dkmdt_video_present_source
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
-	d3dkmdt.h
apiname:
-	D3DKMDT_VIDEO_PRESENT_SOURCE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDEO_PRESENT_SOURCE
---

# _D3DKMDT_VIDEO_PRESENT_SOURCE structure


## -description


The D3DKMDT_VIDEO_PRESENT_SOURCE structure contains the unique identifier of a video present source.


## -syntax


````
typedef struct _D3DKMDT_VIDEO_PRESENT_SOURCE {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID Id;
  DWORD                          dwReserved;
} D3DKMDT_VIDEO_PRESENT_SOURCE;
````


## -struct-fields




### -field Id

The identifier of a video present source.


### -field dwReserved

Reserved for future use.


## -remarks



The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

Video present source identifiers are assigned by the operating system. <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... NÂ -Â 1.

For more information about video present sources, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a>.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_video_present_target.md">D3DKMDT_VIDEO_PRESENT_TARGET</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDEO_PRESENT_SOURCE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

