---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET
title: DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET
author: windows-driver-content
description: The pfnGetPathSourceFromTarget function returns the identifier of the video present source that is associated with a specified video present target.
old-location: display\dxgk_vidpntopology_interface_pfngetpathsourcefromtarget.htm
old-project: display
ms.assetid: c3e7b025-2382-4a81-8d78-9333b62b556a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_vidpntopology_interface_pfngetpathsourcefromtarget, pfnGetPathSourceFromTarget callback function [Display Devices], pfnGetPathSourceFromTarget, DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET, DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET, d3dkmddi/pfnGetPathSourceFromTarget, VidPnFunctions_a6324165-7203-455f-8b96-40cf1a0dfb14.xml
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
-	pfnGetPathSourceFromTarget
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET callback


## -description


The <b>pfnGetPathSourceFromTarget</b> function returns the identifier of the video present source that is associated with a specified video present target.


## -prototype


````
DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET pfnGetPathSourceFromTarget;

NTSTATUS APIENTRY pfnGetPathSourceFromTarget(
  _In_  const D3DKMDT_HVIDPNTOPOLOGY         hVidTopology,
  _In_  const D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId,
  _Out_       D3DDDI_VIDEO_PRESENT_SOURCE_ID *pVidPnSourceId
)
{ ... }
````


## -parameters




### -param hVidTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnTargetId [in]

[in] An integer that identifies a particular video present source.


### -param pVidPnSourceId [out]

[out] A pointer to a variable that receives the identifier of the video present source.


## -returns



The <b>pfnGetPathSourceFromTarget</b> function returns one of the following values:

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer supplied in <i>pVidPnSourceId</i> was in valid.

</td>
</tr>
</table>
 




## -remarks



A topology is a collection paths, each of which contains a (source, target) pair. A particular target belongs to at most one path, so given a target ID, there is at most one source associated with that target.

VidPN source identifiers are assigned by the operating system. <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

VidPN target identifiers are assigned by the display miniport driver. <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>. 




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_enumpathtargetsfromsource.md">pfnEnumPathTargetsFromSource</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

