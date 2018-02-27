---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWINSTANCED
title: PFND3D10DDI_DRAWINSTANCED
author: windows-driver-content
description: The DrawInstanced function draws particular instances of nonindexed primitives.
old-location: display\drawinstanced.htm
old-project: display
ms.assetid: c539cf8b-e056-476a-9b23-7e360917a7d9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DrawInstanced, DrawInstanced callback function [Display Devices], PFND3D10DDI_DRAWINSTANCED, UserModeDisplayDriverDx10_Functions_15fe8a07-36ca-4ab1-8570-01250eed4866.xml, d3d10umddi/DrawInstanced, display.drawinstanced
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	DrawInstanced
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_DRAWINSTANCED callback


## -description


The <b>DrawInstanced</b> function draws particular instances of nonindexed primitives.


## -prototype


````
PFND3D10DDI_DRAWINSTANCED DrawInstanced;

VOID APIENTRY DrawInstanced(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ UINT             VertexCountPerInstance,
  _In_ UINT             InstanceCount,
  _In_ UINT             StartVertexLocation,
  _In_ UINT             StartInstanceLocation
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param UINT








#### - InstanceCount [in]

 The number of instances of the buffer that vertices are read from to draw the primitives. 


#### - StartInstanceLocation [in]

 The first instance of the buffer that vertices are read from to draw the primitives. 


#### - StartVertexLocation [in]

 The first vertex in the buffer that vertices are read from to draw the primitives. 


#### - VertexCountPerInstance [in]

 The number of vertices per instance of the buffer that vertices are read from to draw the primitives. 


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DrawInstanced</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_DRAWINSTANCED callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

