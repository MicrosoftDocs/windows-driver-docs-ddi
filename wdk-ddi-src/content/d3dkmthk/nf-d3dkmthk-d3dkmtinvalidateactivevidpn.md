---
UID: NF:d3dkmthk.D3DKMTInvalidateActiveVidPn
title: D3DKMTInvalidateActiveVidPn function
author: windows-driver-content
description: The D3DKMTInvalidateActiveVidPn function invalidates the active video present network (VidPN) currently in use.Note   This function is obsolete in Windows 7 and later versions of the Windows operating systems.
old-location: display\d3dkmtinvalidateactivevidpn.htm
old-project: display
ms.assetid: a7cac46d-b64d-4362-99ab-179aa6525ba2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTInvalidateActiveVidPn, D3DKMTInvalidateActiveVidPn function [Display Devices], OpenGL_Functions_3c74c218-cf17-4a86-af8e-da565b3cffd4.xml, d3dkmthk/D3DKMTInvalidateActiveVidPn, display.d3dkmtinvalidateactivevidpn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems for display miniport drivers with version < DXGKDDI_INTERFACE_VERSION_WIN7.
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTInvalidateActiveVidPn
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTInvalidateActiveVidPn function


## -description


The <b>D3DKMTInvalidateActiveVidPn</b> function invalidates the active video present network (VidPN) currently in use.


<div class="alert"><b>Note</b>    This function is obsolete in Windows 7 and later versions of the Windows operating systems.</div>
<div> </div>



## -syntax


````
NTSTATUS D3DKMTInvalidateActiveVidPn(
  _In_ const D3DKMT_INVALIDATEACTIVEVIDPN *pData
);
````


## -parameters




### -param D3DKMT_INVALIDATEACTIVEVIDPN

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md">D3DKMT_INVALIDATEACTIVEVIDPN</a> structure that describes parameters that invalidate the active VidPN currently in use.


## -returns



<b>D3DKMTInvalidateActiveVidPn</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The VidPN currently in use was successfully invalidated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER</b></dt>
</dl>
</td>
<td width="60%">
No graphics adapter was specified in the <b>hAdapter</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md">D3DKMT_INVALIDATEACTIVEVIDPN</a> to invalidate the VidPN for.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtinvalidateactivevidpn.md">D3DKMTInvalidateActiveVidPn</a> could not complete because of insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The display mode that is requested by the OpenGL installable client driver (ICD) in the buffer pointed to by the <b>pPrivateDriverData</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md">D3DKMT_INVALIDATEACTIVEVIDPN</a> is not supported by the display miniport driver.

This status value will also be returned if this function is called on a computer running Windows 7 and later by a display miniport driver with DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WIN7.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_NO_RECOMMENDED_FUNCTIONAL_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver did not recommend a VidPN to replace the VidPN currently in use.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



When the <b>D3DKMTInvalidateActiveVidPn</b> function is called to invalidate the VidPN currently in use, the current VidPN is replaced with a new VidPN that the display miniport driver recommends. Because the display miniport driver must recommend a new VidPN, the display miniport driver must be able to determine the display mode that the OpenGL ICD requires from the buffer pointed to by the <b>pPrivateDriverData</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md">D3DKMT_INVALIDATEACTIVEVIDPN</a>.

The OpenGL ICD can call <b>D3DKMTInvalidateActiveVidPn</b> for display modes (for example, clone-view mode) that are not supported by using the more general call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetdisplaymode.md">D3DKMTSetDisplayMode</a> function. 




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md">D3DKMT_INVALIDATEACTIVEVIDPN</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetdisplaymode.md">D3DKMTSetDisplayMode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTInvalidateActiveVidPn function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

