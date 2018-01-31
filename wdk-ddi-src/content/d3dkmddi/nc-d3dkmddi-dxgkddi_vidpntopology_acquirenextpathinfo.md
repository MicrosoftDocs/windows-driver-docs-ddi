---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO
author: windows-driver-content
description: The pfnAcquireNextPathInfo function returns a descriptor of the next video present path in a specified VidPN topology, given the current path.
old-location: display\dxgk_vidpntopology_interface_pfnacquirenextpathinfo.htm
old-project: display
ms.assetid: 9f09ac0e-057c-48fb-a246-35e8ed7ddfc2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpntopology_interface_pfnacquirenextpathinfo, pfnAcquireNextPathInfo callback function [Display Devices], pfnAcquireNextPathInfo, DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO, DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO, d3dkmddi/pfnAcquireNextPathInfo, VidPnFunctions_c06f9c56-bcfd-49a8-a723-4166d7f5129f.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	pfnAcquireNextPathInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO callback


## -description


The <b>pfnAcquireNextPathInfo</b> function returns a descriptor of the next video present path in a specified VidPN topology, given the current path.


## -prototype


````
DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO pfnAcquireNextPathInfo;

NTSTATUS APIENTRY pfnAcquireNextPathInfo(
  _In_  const D3DKMDT_HVIDPNTOPOLOGY           hVidPnTopology,
  _In_  const D3DKMDT_VIDPN_PRESENT_PATH CONST *pVidPnPresentPathInfo,
  _Out_ const D3DKMDT_VIDPN_PRESENT_PATH       **ppNextVidPnPresentPathInfo
)
{ ... }
````


## -parameters




#### - hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


#### - pVidPnPresentPathInfo [in]

[in] A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure that describes the current path. The display miniport driver previously obtained this pointer by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md">pfnAcquireFirstPathInfo</a> or <b>pfnAcquireNextPathInfo</b>.


#### - ppNextVidPnPresentPathInfo [out]

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that describes the next path.


## -returns


The <b>pfnAcquireNextPathInfo</b> function returns one of the following values:
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


When you have finished using the D3DKMDT_VIDPN_PRESENT_PATH structure, you must release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>.

You can enumerate all the paths that belong to a VidPN topology object by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md">pfnAcquireFirstPathInfo</a> and then making a sequence of calls to <b>pfnAcquireNextPathInfo</b>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.



## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo.md">pfnAcqirePathInfo</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md">pfnAcquireFirstPathInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

