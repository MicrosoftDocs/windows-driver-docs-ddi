---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO
author: windows-driver-content
description: The pfnAcquireFirstPathInfo structure returns a descriptor of the first path in a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnacquirefirstpathinfo.htm
old-project: display
ms.assetid: b5dc35dc-f4fb-4209-9a4d-50dc11f16216
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpntopology_interface_pfnacquirefirstpathinfo, pfnAcquireFirstPathInfo callback function [Display Devices], pfnAcquireFirstPathInfo, DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO, DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO, d3dkmddi/pfnAcquireFirstPathInfo, VidPnFunctions_d45dd9b3-775b-41a6-a5e4-8fb226ed7ea4.xml
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
-	pfnAcquireFirstPathInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO callback


## -description


The <b>pfnAcquireFirstPathInfo</b> structure returns a descriptor of the first path in a specified VidPN topology object.


## -prototype


````
DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO pfnAcquireFirstPathInfo;

NTSTATUS APIENTRY pfnAcquireFirstPathInfo(
  _In_  const D3DKMDT_HVIDPNTOPOLOGY           hVidPnTopology,
  _Out_ const D3DKMDT_VIDPN_PRESENT_PATH CONST **ppFirstVidPnPresentPathInfo
)
{ ... }
````


## -parameters




#### - hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


#### - ppFirstVidPnPresentPathInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure. The structure contains a variety of information about the path, including the path's source and target identifiers.


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


When you have finished using the D3DKMDT_VIDPN_PRESENT_PATH structure, you must release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>.

You can enumerate all the paths that belong to a VidPN topology object by calling <b>pfnAcquireFirstPathInfo</b> and then making a sequence of calls to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo.md">pfnAcquireNextPathInfo</a>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.



## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo.md">pfnAcqirePathInfo</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo.md">pfnAcquireNextPathInfo</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

