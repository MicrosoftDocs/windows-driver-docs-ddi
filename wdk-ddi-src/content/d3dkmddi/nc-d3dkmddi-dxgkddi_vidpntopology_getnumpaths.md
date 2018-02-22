---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS
title: DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS
author: windows-driver-content
description: The pfnGetNumPaths function returns the number of video present paths in a specified VidPN topology.
old-location: display\dxgk_vidpntopology_interface_pfngetnumpaths.htm
old-project: display
ms.assetid: 60960774-3f90-4eeb-a408-fa37122f22ea
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_vidpntopology_interface_pfngetnumpaths, pfnGetNumPaths callback function [Display Devices], pfnGetNumPaths, DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS, DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS, d3dkmddi/pfnGetNumPaths, VidPnFunctions_c330d233-9a8e-4c53-a73e-b789fb2cb7b0.xml
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
-	pfnGetNumPaths
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS callback


## -description


The <b>pfnGetNumPaths</b> function returns the number of video present paths in a specified VidPN topology.


## -prototype


````
DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS pfnGetNumPaths;

NTSTATUS APIENTRY pfnGetNumPaths(
  _In_  const D3DKMDT_HVIDPNTOPOLOGY hVidPnTopology,
  _Out_       SIZE_T                 *pNumPaths
)
{ ... }
````


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param pNumPaths [out]

[out] A pointer to a SIZE_T-typed variable that receives the number of paths.


## -returns



The <b>pfnGetNumPaths</b> function returns one of the following values:

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



The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_getnumpathsfromsource.md">pfnGetNumPathsFromSource</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

