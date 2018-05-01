---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCEMAP
title: PFND3D10DDI_RESOURCEMAP
author: windows-driver-content
description: The ResourceMap function maps a subresource of a resource.
old-location: display\resourcemap.htm
old-project: display
ms.assetid: 1310a3f8-02dd-4d35-98ad-4016e57d1eb2
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D10DDI_RESOURCEMAP, PFND3D10DDI_RESOURCEMAP callback, ResourceMap, ResourceMap callback function [Display Devices], UserModeDisplayDriverDx10_Functions_2c1f2d21-4d2c-4e3f-993d-c6af5177e793.xml, d3d10umddi/ResourceMap, display.resourcemap
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
-	ResourceMap
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_RESOURCEMAP callback function


## -description


The <i>ResourceMap</i> function maps a subresource of a resource.


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param Arg4


### -param Arg5


### -param *








#### - DDIMap [in]

 A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541957">D3D10_DDI_MAP</a>-typed value that indicates the access level to map the subresource to. 


#### - Flags [in]

 A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541959">D3D10_DDI_MAP_FLAG</a>-typed value that indicates how to map the subresource. 


#### - Subresource [in]

 An index that indicates the subresource to map. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hResource [in]

 A handle to the resource to map.


#### - pMappedSubResource [out]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541839">D3D10DDI_MAPPED_SUBRESOURCE</a> structure that receives the information about the mapped subresource.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section. 




## -remarks



The driver can call <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> to set the D3DDDIERR_DEVICEREMOVED error code.

Typically, immediately after the runtime receives the D3DDDIERR_DEVICEREMOVED error code, the runtime will no longer call into the user-mode display driver for much (other than for unbinding, destruction, and other cleanup operations).  

Typically, each call to the user-mode display driver's <i>ResourceMap</i> function is accompanied with a call to the driver's <a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a> function; however, after the runtime receives the D3DDDIERR_DEVICEREMOVED error code, it will not call <i>ResourceUnmap</i>.

If the runtime passed the D3D10_DDI_MAP_FLAG_DONOTWAIT flag in the <i>Flags</i> parameter, the driver can call <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> to set the DXGI_DDI_ERR_WASSTILLDRAWING error code.

The driver can implement one pair of <i>ResourceMap</i> and <i>ResourceUnmap</i> functions that can contain <b>switch</b> statements to process various functionalities. That is, the driver can implement one <i>ResourceMap</i>-<i>ResourceUnmap</i> pair and can set the following members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a> structure to point to this implementation pair:

<ul>
<li>
<b>pfnDynamicIABufferMapDiscard</b>-<b>pfnDynamicIABufferUnmap</b>

</li>
<li>
<b>pfnDynamicIABufferMapNoOverwrite</b>-<b>pfnDynamicIABufferUnmap</b>

</li>
<li>
<b>pfnDynamicConstantBufferMapDiscard</b>-<b>pfnDynamicConstantBufferUnmap</b>

</li>
<li>
<b>pfnDynamicResourceMapDiscard</b>-<b>pfnDynamicResourceUnmap</b>

</li>
<li>
<b>pfnStagingResourceMap</b>-<b>pfnStagingResourceUnmap</b>

</li>
</ul>
However, to improve performance, the driver can implement separate map-unmap function pairs. The Microsoft Direct3D runtime calls the appropriate map-unmap function pair depending on the resource type (for example, a buffer or texture) and the type of <a href="https://msdn.microsoft.com/library/windows/hardware/ff542008">D3D10_DDI_RESOURCE_USAGE</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541995">D3D10_DDI_RESOURCE_BIND_FLAG</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541957">D3D10_DDI_MAP</a> values that are specified when the resource is created and mapped.

<div class="alert"><b>Note</b>    If the resource type to map and unmap is a buffer, the Direct3D runtime sets the <i>Subresource</i> parameter to zero.</div>
<div> </div>
<div class="alert"><b>Note</b>    Although the Direct3D runtime typically calls the <b>pfnDynamicResourceMapDiscard</b>-<b>pfnDynamicResourceUnmap</b> function pair for dynamic textures, the runtime also calls this function pair for dynamic buffers that were created with the D3D10_DDI_BIND_SHADER_RESOURCE bind flag set.</div>
<div> </div>
The following example code shows the values that are set when the Direct3D runtime calls specific map or unmap function:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//-----------------------------------------------
void APIENTRY UMDevice::DynamicIABufferMapNoOverwrite_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource,
    D3D10_DDI_MAP MapType,
    UINT MapFlags,
    D3D10DDI_MAPPED_SUBRESOURCE* pMappedSubresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.ResourceDimension == D3D10DDIRESOURCE_BUFFER &amp;&amp;
        pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_DYNAMIC &amp;&amp;
        (pResource-&gt;m_DDICreateResource.BindFlags &amp; (D3D10_DDI_BIND_VERTEX_BUFFER | D3D10_DDI_BIND_INDEX_BUFFER)) &amp;&amp;
        !(pResource-&gt;m_DDICreateResource.BindFlags &amp; ~(D3D10_DDI_BIND_VERTEX_BUFFER | D3D10_DDI_BIND_INDEX_BUFFER)) &amp;&amp;
        Subresource == 0 &amp;&amp;
        MapType == D3D10_DDI_MAP_WRITE_NOOVERWRITE &amp;&amp;
        MapFlags == 0 );
 
    pResource-&gt;Map( Subresource, MapType, MapFlags, pMappedSubresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::DynamicIABufferMapDiscard_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource,
    D3D10_DDI_MAP MapType,
    UINT MapFlags,
    D3D10DDI_MAPPED_SUBRESOURCE* pMappedSubresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.ResourceDimension == D3D10DDIRESOURCE_BUFFER &amp;&amp;
        pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_DYNAMIC &amp;&amp;
        (pResource-&gt;m_DDICreateResource.BindFlags &amp; (D3D10_DDI_BIND_VERTEX_BUFFER | D3D10_DDI_BIND_INDEX_BUFFER)) &amp;&amp;
        !(pResource-&gt;m_DDICreateResource.BindFlags &amp; ~(D3D10_DDI_BIND_VERTEX_BUFFER | D3D10_DDI_BIND_INDEX_BUFFER)) &amp;&amp;
        Subresource == 0 &amp;&amp;
        MapType == D3D10_DDI_MAP_WRITE_DISCARD &amp;&amp;
        MapFlags == 0 );
 
    pResource-&gt;Map( Subresource, MapType, MapFlags, pMappedSubresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::DynamicIABufferUnmap_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.ResourceDimension == D3D10DDIRESOURCE_BUFFER &amp;&amp;
        pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_DYNAMIC &amp;&amp;
        (pResource-&gt;m_DDICreateResource.BindFlags &amp; (D3D10_DDI_BIND_VERTEX_BUFFER | D3D10_DDI_BIND_INDEX_BUFFER)) &amp;&amp;
        !(pResource-&gt;m_DDICreateResource.BindFlags &amp; ~(D3D10_DDI_BIND_VERTEX_BUFFER | D3D10_DDI_BIND_INDEX_BUFFER)) &amp;&amp;
        Subresource == 0 );
 
    pResource-&gt;Unmap( Subresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::DynamicConstantBufferMapDiscard_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource,
    D3D10_DDI_MAP MapType,
    UINT MapFlags,
    D3D10DDI_MAPPED_SUBRESOURCE* pMappedSubresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.ResourceDimension == D3D10DDIRESOURCE_BUFFER &amp;&amp;
        pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_DYNAMIC &amp;&amp;
        (pResource-&gt;m_DDICreateResource.BindFlags &amp; D3D10_DDI_BIND_CONSTANT_BUFFER) &amp;&amp;
        !(pResource-&gt;m_DDICreateResource.BindFlags &amp; ~D3D10_DDI_BIND_CONSTANT_BUFFER) &amp;&amp;
        Subresource == 0 &amp;&amp;
        MapType == D3D10_DDI_MAP_WRITE_DISCARD &amp;&amp;
        MapFlags == 0 );
 
    pResource-&gt;Map( Subresource, MapType, MapFlags, pMappedSubresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::DynamicConstantBufferUnmap_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.ResourceDimension == D3D10DDIRESOURCE_BUFFER &amp;&amp;
        pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_DYNAMIC &amp;&amp;
        (pResource-&gt;m_DDICreateResource.BindFlags &amp; D3D10_DDI_BIND_CONSTANT_BUFFER) &amp;&amp;
        !(pResource-&gt;m_DDICreateResource.BindFlags &amp; ~D3D10_DDI_BIND_CONSTANT_BUFFER) &amp;&amp;
        Subresource == 0 );
 
    pResource-&gt;Unmap( Subresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::DynamicResourceMapDiscard_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource,
    D3D10_DDI_MAP MapType,
    UINT MapFlags,
    D3D10DDI_MAPPED_SUBRESOURCE* pMappedSubresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_DYNAMIC &amp;&amp;
        pResource-&gt;m_DDICreateResource.Subresources == 1 &amp;&amp;
        Subresource == 0 &amp;&amp;
        MapType == D3D10_DDI_MAP_WRITE_DISCARD &amp;&amp;
        MapFlags == 0 );
 
    pResource-&gt;Map( Subresource, MapType, MapFlags, pMappedSubresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::DynamicResourceUnmap_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_DYNAMIC &amp;&amp;
        pResource-&gt;m_DDICreateResource.Subresources == 1 &amp;&amp;
        Subresource == 0 );
 
    pResource-&gt;Unmap( Subresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::StagingResourceMap_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource,
    D3D10_DDI_MAP MapType,
    UINT MapFlags,
    D3D10DDI_MAPPED_SUBRESOURCE* pMappedSubresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_STAGING &amp;&amp;
        (MapType == D3D10_DDI_MAP_READ || MapType == D3D10_DDI_MAP_WRITE || MapType == D3D10_DDI_MAP_READWRITE) );
 
    pResource-&gt;Map( Subresource, MapType, MapFlags, pMappedSubresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::StagingResourceUnmap_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.Usage == D3D10_DDI_USAGE_STAGING );
 
    pResource-&gt;Unmap( Subresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::ResourceMap_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource,
    D3D10_DDI_MAP MapType,
    UINT MapFlags,
    D3D10DDI_MAPPED_SUBRESOURCE* pMappedSubresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.Usage != D3D10_DDI_USAGE_DYNAMIC &amp;&amp;
        pResource-&gt;m_DDICreateResource.Usage != D3D10_DDI_USAGE_STAGING );
 
    // Generally true; but allow last second change:
    assert( false );
 
    pResource-&gt;Map( Subresource, MapType, MapFlags, pMappedSubresource );
}
 
//------------------------------------------------
void APIENTRY UMDevice::ResourceUnmap_Default(
    D3D10DDI_HDEVICE hDevice,
    D3D10DDI_HRESOURCE hResource,
    UINT Subresource )
{
    UMDevice* pThis = UMDevice::CastFrom( hDevice );
    UMResource* pResource = UMResource::CastFrom( hResource );
 
    assert( pResource-&gt;m_DDICreateResource.Usage != D3D10_DDI
_USAGE_DYNAMIC &amp;&amp;
        pResource-&gt;m_DDICreateResource.Usage != D3D10_DDI_USAGE_STAGING );
 
    // Generally true; but allow last second change:
    assert( false );
 
    pResource-&gt;Unmap( Subresource );
}</pre>
</td>
</tr>
</table></span></div>
<h3><a id="Restrictions_on_input_values"></a><a id="restrictions_on_input_values"></a><a id="RESTRICTIONS_ON_INPUT_VALUES"></a>Restrictions on input values</h3>
For Windows Display Driver Model (WDDM) 1.3 and later drivers, the Microsoft Direct3D runtime supplies a restricted set of input values used by this function. For a list of all restricted values, see <a href="https://msdn.microsoft.com/F9AAE489-EC45-4EE6-875E-E084BB3054EE">Direct3D rendering performance improvements</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541839">D3D10DDI_MAPPED_SUBRESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541957">D3D10_DDI_MAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541959">D3D10_DDI_MAP_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541995">D3D10_DDI_RESOURCE_BIND_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542008">D3D10_DDI_RESOURCE_USAGE</a>



<a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

