---
UID: NC:d3d10umddi.PFND3D10DDI_CLEARDEPTHSTENCILVIEW
title: PFND3D10DDI_CLEARDEPTHSTENCILVIEW
author: windows-driver-content
description: The ClearDepthStencilView function clears the specified currently bound depth-stencil view.
old-location: display\cleardepthstencilview.htm
old-project: display
ms.assetid: 0474c154-1bec-4602-880c-ffdc48c738f0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ClearDepthStencilView, ClearDepthStencilView callback function [Display Devices], PFND3D10DDI_CLEARDEPTHSTENCILVIEW, UserModeDisplayDriverDx10_Functions_580c85a3-3ad9-415c-925c-2ca103d10237.xml, d3d10umddi/ClearDepthStencilView, display.cleardepthstencilview
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
-	ClearDepthStencilView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CLEARDEPTHSTENCILVIEW callback


## -description


The <b>ClearDepthStencilView</b> function clears the specified currently bound depth-stencil view. 


## -prototype


````
PFND3D10DDI_CLEARDEPTHSTENCILVIEW ClearDepthStencilView;

VOID APIENTRY ClearDepthStencilView(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D10DDI_HDEPTHSTENCILVIEW hDepthStencilView,
  _In_ UINT                       Flags,
  _In_ FLOAT                      Depth,
  _In_ UINT8                      Stencil
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HDEPTHSTENCILVIEW


### -param UINT


### -param FLOAT


### -param UINT8








#### - Depth [in]

 A single-precision float vector to set the depth to. 


#### - Flags [in]

 A value that specifies which parts of the buffer to affect. This parameter must be set to one of the following values from the D3D10_DDI_CLEAR_FLAG enumeration.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D10_DDI_CLEAR_DEPTH (0x01L)

</td>
<td>
The depth value (Z) is clamped to the ZNear and ZFar range of the viewport that is currently bound to slot zero by using Microsoft Direct3D. Afterwards, Z is clamped again to the representable range of the currently bound depth-stencil view by again using Direct3D.

</td>
</tr>
<tr>
<td>
D3D10_DDI_CLEAR_STENCIL (0x02L)

</td>
<td>
The stencil value is cleared.

</td>
</tr>
</table>
 


#### - Stencil [in]

 An unsigned 8-bit integer value to set the stencil to. 


#### - hDepthStencilView [in]

 A handle to the depth-stencil view to clear. 


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



Floating point rules apply to the <b>ClearDepthStencilView</b> function. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>ClearDepthStencilView</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CLEARDEPTHSTENCILVIEW callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

