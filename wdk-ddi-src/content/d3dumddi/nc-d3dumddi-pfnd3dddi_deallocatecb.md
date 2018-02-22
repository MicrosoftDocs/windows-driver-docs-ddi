---
UID: NC:d3dumddi.PFND3DDDI_DEALLOCATECB
title: PFND3DDDI_DEALLOCATECB
author: windows-driver-content
description: The pfnDeallocateCb callback function releases allocations or a kernel-mode resource object if the resource object was created.
old-location: display\pfndeallocatecb.htm
old-project: display
ms.assetid: 2ffa0367-0451-45d2-be05-e450c45be116
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfndeallocatecb, pfnDeallocateCb callback function [Display Devices], pfnDeallocateCb, PFND3DDDI_DEALLOCATECB, PFND3DDDI_DEALLOCATECB, d3dumddi/pfnDeallocateCb, D3Druntime_Functions_0162df86-f479-45d9-887b-75f05de150f9.xml
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
-	pfnDeallocateCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DEALLOCATECB callback


## -description


The <b>pfnDeallocateCb</b> callback function releases allocations or a kernel-mode resource object if the resource object was created.


## -prototype


````
PFND3DDDI_DEALLOCATECB pfnDeallocateCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnDeallocateCb(
  _In_       HANDLE              hDevice,
  _In_ const D3DDDICB_DEALLOCATE *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_deallocate.md">D3DDDICB_DEALLOCATE</a> structure that describes the resource to release.


## -returns



<b>pfnDeallocateCb</b> returns one of the following values:

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
The memory was successfully released.

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



The user-mode display driver can release allocations in the following ways: 

<ul>
<li>
Individually, by setting the <b>hResource</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_deallocate.md">D3DDDICB_DEALLOCATE</a> structure that is pointed to by <i>pData </i>to <b>NULL</b> and populating the array in the <b>HandleList</b> member of D3DDDICB_DEALLOCATE with handles of the allocations to release 

</li>
<li>
In a group, by setting <b>hResource</b> to a resource handle whose allocations are to be released. If <b>hResource</b> is non-<b>NULL</b>, the <b>HandleList</b> and <b>NumAllocations</b> members of D3DDDICB_DEALLOCATE are ignored. 

</li>
</ul>
Note that if the user-mode display driver sets <b>hResource</b> to <b>NULL</b> and populates all array elements in <b>HandleList</b> to release all allocations, the driver must subsequently call the <b>pfnDeallocateCb</b> function again to only release the resource by setting <b>hResource</b> to the handle to the resource.

Note that the <b>pfnDeallocateCb</b> function is distinct from the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyresource.md">DestroyResource</a> or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyresource.md">DestroyResource(D3D10)</a> function. However, the user-mode display driver typically calls <b>pfnDeallocateCb</b> in response to a call to its <i>DestroyResource</i> or <b>DestroyResource(D3D10)</b> function. 

<b>Direct3D Version 9 Note:  </b>For more information about creating and destroying resources, see <a href="https://msdn.microsoft.com/d443bdc3-1c5a-4372-9e6a-b8a4d21499b9">Handling Resource Creation and Destruction</a>.

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnDeallocateCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.

The following code example shows how to release a resource.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    D3DDDICB_DEALLOCATE deAllocCB;
    HRESULT             hr;
    D3DKMT_HANDLE       hKMAllocHandle;

    memset(&amp;deAllocCB, 0, sizeof(deAllocCB));

    deAllocCB.hResource = m_hCurResRuntime;

    hr = m_d3dCallbacks.pfnDeallocateCb(m_hD3D, &amp;deAllocCB);
    if ((m_hCurResRuntime) &amp;&amp; (SUCCEEDED(hr))) {
        m_bCurResFreed = TRUE;
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_deallocate.md">D3DDDICB_DEALLOCATE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyresource.md">DestroyResource(D3D10)</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyresource.md">DestroyResource</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DEALLOCATECB callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

