---
UID: NC:d3dumddi.PFND3DDDI_QUERYADAPTERINFOCB
title: PFND3DDDI_QUERYADAPTERINFOCB
author: windows-driver-content
description: The pfnQueryAdapterInfoCb function retrieves graphics adapter information.
old-location: display\pfnqueryadapterinfocb.htm
tech.root: display
ms.assetid: 8008574f-a89e-4fed-b745-7cf5baa68e64
ms.date: 5/10/2018
ms.keywords: D3Druntime_Functions_ca5c02c9-ad59-4a10-8cb7-92d815cd6856.xml, PFND3DDDI_QUERYADAPTERINFOCB, PFND3DDDI_QUERYADAPTERINFOCB callback, d3dumddi/pfnQueryAdapterInfoCb, display.pfnqueryadapterinfocb, pfnQueryAdapterInfoCb, pfnQueryAdapterInfoCb callback function [Display Devices]
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
-	pfnQueryAdapterInfoCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_QUERYADAPTERINFOCB callback function


## -description


The <b>pfnQueryAdapterInfoCb</b> function retrieves graphics adapter information.


## -parameters




### -param hAdapter [in]

A handle to the graphics adapter object. 


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544225">D3DDDICB_QUERYADAPTERINFO</a> structure that receives information about the graphics hardware. 


## -returns



<b>pfnQueryAdapterInfoCb</b> returns one of the following values:

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
Information was successfully retrieved.

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
</table>
 

This function might also return other HRESULT values.




## -remarks



Before the Microsoft Direct3D runtime calls the user-mode display driver's <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a> or <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function to create the graphics context, the user-mode display driver should call <b>pfnQueryAdapterInfoCb</b> to retrieve information about the graphics hardware. This order is especially important for a multiple-monitor system. 

In the <b>pfnQueryAdapterInfoCb</b> call, the user-mode display driver sends a buffer that the display miniport driver fills with configuration data. After receiving this configuration data, the user-mode display driver can accurately report its capabilities when the runtime calls the user-mode display driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> and GetCaps(D3D10_2) functions. When the runtime subsequently calls other user-mode display driver functions that are specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a> structure, the user-mode display driver can generate command streams that the hardware can process. 


#### Examples

The following code example shows how to retrieve graphics adapter information.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    HRESULT hr;
    // Query for GART segment support
    D3DDDICB_QUERYADAPTERINFO   ddiQueryAdapterInfo;

    memset(&amp;R200AdapterInfo, 0, sizeof(R200AdapterInfo));

    ddiQueryAdapterInfo.pPrivateDriverData = &amp;R200AdapterInfo;
    ddiQueryAdapterInfo.PrivateDriverDataSize = sizeof(R200AdapterInfo);

    hr = m_Callbacks.pfnQueryAdapterInfoCb(m_hAdapter, &amp;ddiQueryAdapterInfo);
    if (FAILED(hr)) {
        return FALSE;
    }

    m_ulGartSupported = R200AdapterInfo.ulGartSupported;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544225">D3DDDICB_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544350">D3DDDI_ADAPTERCALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

