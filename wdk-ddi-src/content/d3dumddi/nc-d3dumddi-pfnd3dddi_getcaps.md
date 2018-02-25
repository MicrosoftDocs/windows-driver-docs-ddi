---
UID: NC:d3dumddi.PFND3DDDI_GETCAPS
title: PFND3DDDI_GETCAPS
author: windows-driver-content
description: The GetCaps function queries for capabilities of the graphics adapter.
old-location: display\getcaps.htm
old-project: display
ms.assetid: cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GetCaps, GetCaps callback function [Display Devices], PFND3DDDI_GETCAPS, UserModeDisplayDriver_Functions_2848e873-69ef-4b77-b8bc-8ae9f4abe2c9.xml, d3dumddi/GetCaps, display.getcaps
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	GetCaps
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_GETCAPS callback


## -description


The <i>GetCaps</i> function queries for capabilities of the graphics adapter.


## -prototype


````
PFND3DDDI_GETCAPS GetCaps;

__checkReturn HRESULT APIENTRY GetCaps(
  _In_          HANDLE            hAdapter,
  _Inout_ const D3DDDIARG_GETCAPS *pData
)
{ ... }
````


## -parameters




### -param hAdapter [in]

 A handle that identifies the graphics adapter. 


### -param *








#### - pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure that describes the capabilities to retrieve.


## -returns



<i>GetCaps</i> returns one of the following values:

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
The capabilities were successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The data that is returned by the <i>GetCaps</i> function in the <b>pData</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure depends on the type of data that is requested (that is, the data depends on the <b>Type</b> member of <b>D3DDDIARG_GETCAPS</b> and sometimes on the <b>pInfo</b> member).

Here are examples of how to set up the <i>GetCaps</i> call depending on the value of <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>.<b>Type</b>.

<table>
<tr>
<th>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> member</th>
<th>Member value—Example 1</th>
<th>Member value—Example 2</th>
</tr>
<tr>
<td><b>Type</b></td>
<td><b>D3DDDICAPS_DDRAW</b></td>
<td><b>D3DDDICAPS_GETFORMATCOUNT</b></td>
</tr>
<tr>
<td><b>pInfo</b></td>
<td>[in] <code>NULL</code> (no conditions are set)</td>
<td>[in] <code>NULL</code> (no conditions are set)</td>
</tr>
<tr>
<td><b>pData</b></td>
<td>[out] <code>DDRAW_CAPS*</code> (unique pointer)</td>
<td>[out] <code>UINT*</code> (unique pointer)</td>
</tr>
<tr>
<td><b>DataSize</b></td>
<td><code>sizeof(DDRAW_CAPS)</code></td>
<td><code>sizeof(UINT)</code></td>
</tr>
<tr>
<td><b>Notes</b></td>
<td>Driver must fill in the <a href="..\d3dumddi\ns-d3dumddi-_ddraw_caps.md">DDRAW_CAPS</a> structure pointed to by <b>pData</b> with Microsoft DirectDraw capabilities that it supports.</td>
<td>Driver must fill the buffer pointed to by <b>pData</b> with a UINT value that represents the number of <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> surface formats that the device supports.</td>
</tr>
</table>
 

See the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> enumeration topic for explanations of other values for <b>D3DDDIARG_GETCAPS</b>.<b>Type</b> that are used for multiplane overlays.

<h3><a id="Simple_instancing"></a><a id="simple_instancing"></a><a id="SIMPLE_INSTANCING"></a>Simple instancing</h3>
If a Microsoft Direct3D Level 9 driver that supports Windows Display Driver Model (WDDM) 1.3 and later completes a call to <i>GetCaps</i> and returns <b>S_OK</b> but doesn't change the data in the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure, it indicates to the Direct3D runtime that the hardware and driver don't support simple instancing. For more info, see <a href="..\d3dumddi\ns-d3dumddi-d3dddicaps_simple_instancing_support.md">D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT</a>.




## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



<a href="..\d3dumddi\ns-d3dumddi-d3dddicaps_simple_instancing_support.md">D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT</a>



<a href="..\d3dumddi\ns-d3dumddi-_ddraw_caps.md">DDRAW_CAPS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_adapterfuncs.md">D3DDDI_ADAPTERFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_GETCAPS callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

