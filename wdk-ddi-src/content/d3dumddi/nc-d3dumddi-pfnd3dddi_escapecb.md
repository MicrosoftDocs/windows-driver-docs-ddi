---
UID: NC:d3dumddi.PFND3DDDI_ESCAPECB
title: PFND3DDDI_ESCAPECB
author: windows-driver-content
description: The pfnEscapeCb callback function shares information with the display miniport driver.
old-location: display\pfnescapecb.htm
old-project: display
ms.assetid: 66c0347f-2cf3-42fc-8641-47c731e958c9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3Druntime_Functions_8c7e48ef-f8e8-45d2-a424-9065e97f725f.xml, PFND3DDDI_ESCAPECB, d3dumddi/pfnEscapeCb, display.pfnescapecb, pfnEscapeCb, pfnEscapeCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	pfnEscapeCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_ESCAPECB callback


## -description


The <b>pfnEscapeCb</b> callback function shares information with the display miniport driver.


## -prototype


````
PFND3DDDI_ESCAPECB pfnEscapeCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnEscapeCb(
  _In_          HANDLE          hAdapter,
  _Inout_ const D3DDDICB_ESCAPE *pData
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to the graphics adapter object.


### -param *








#### - pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_escape.md">D3DDDICB_ESCAPE</a> structure that describes the shared information.


## -returns



<b>pfnEscapeCb</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
Information was successfully shared.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnEscapeCb</b> could not complete because of insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">

        Parameters were validated and determined to be incorrect.
       

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnEscapeCb</b> could not initiate a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a> function because a Plug and Play (PnP) stop or a Timeout Detection and Recovery (TDR) event occurred. The user-mode display driver function that called <b>pfnEscapeCb</b> must return this error code back to the Direct3D runtime. 

<b>Direct3D Version 9 Note:  </b>For more information about returning error codes, see <a href="https://msdn.microsoft.com/4a2384e8-407f-4248-8b31-7c4e836b15dc">Returning Error Codes Received from Runtime Functions</a>.

<b>Direct3D Versions 10 and 11 Note:  </b>If the driver function does not return a value (that is, has VOID for a return parameter type), the driver function calls the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function to send an error code back to the runtime. For more information about handling error codes, see <a href="https://msdn.microsoft.com/ac4e056e-3304-4934-887a-5cc2b87989bd">Handling Errors</a>.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.




## -remarks



A user-mode display driver calls <b>pfnEscapeCb</b> to share miscellaneous information with the display miniport driver in a way that is not supported by any other driver communication. The user-mode display driver can send miscellaneous information to the display miniport driver or can retrieve information from the display miniport driver. 

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnEscapeCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_escape.md">D3DDDICB_ESCAPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_ESCAPECB callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

