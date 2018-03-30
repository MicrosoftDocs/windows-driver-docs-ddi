---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO
author: windows-driver-content
description: The pfnAcquireFirstPathInfo structure returns a descriptor of the first path in a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnacquirefirstpathinfo.htm
old-project: display
ms.assetid: b5dc35dc-f4fb-4209-9a4d-50dc11f16216
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO, VidPnFunctions_d45dd9b3-775b-41a6-a5e4-8fb226ed7ea4.xml, d3dkmddi/pfnAcquireFirstPathInfo, display.dxgk_vidpntopology_interface_pfnacquirefirstpathinfo, pfnAcquireFirstPathInfo, pfnAcquireFirstPathInfo callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnAcquireFirstPathInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO callback


## -description


The <b>pfnAcquireFirstPathInfo</b> structure returns a descriptor of the first path in a specified VidPN topology object.


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param ppFirstVidPnPresentPathInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure. The structure contains a variety of information about the path, including the path's source and target identifiers.


## -returns



The <b>pfnAcquireFirstPathInfo</b> function returns one of the following values:

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
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTopology </i>was invalid.

</td>
</tr>
</table>
 




## -remarks



When you have finished using the D3DKMDT_VIDPN_PRESENT_PATH structure, you must release the structure by calling <a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>.

You can enumerate all the paths that belong to a VidPN topology object by calling <b>pfnAcquireFirstPathInfo</b> and then making a sequence of calls to <a href="https://msdn.microsoft.com/9f09ac0e-057c-48fb-a246-35e8ed7ddfc2">pfnAcquireNextPathInfo</a>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://msdn.microsoft.com/27a03106-a5b5-489c-968a-81b3ea9940cb">pfnAcqirePathInfo</a>



<a href="https://msdn.microsoft.com/9f09ac0e-057c-48fb-a246-35e8ed7ddfc2">pfnAcquireNextPathInfo</a>



<a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>
 

 

