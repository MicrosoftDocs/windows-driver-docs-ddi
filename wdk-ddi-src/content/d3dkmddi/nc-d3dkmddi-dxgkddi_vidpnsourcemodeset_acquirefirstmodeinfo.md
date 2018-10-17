---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_ACQUIREFIRSTMODEINFO
title: DXGKDDI_VIDPNSOURCEMODESET_ACQUIREFIRSTMODEINFO
author: windows-driver-content
description: The pfnAcquireFirstModeInfo function returns a descriptor of the first mode in a specified VidPN source mode set.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnacquirefirstmodeinfo.htm
ms.assetid: 3af816e0-f1a4-4477-8735-6400aadfb57b
ms.date: 5/10/2018
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_ACQUIREFIRSTMODEINFO, DXGKDDI_VIDPNSOURCEMODESET_ACQUIREFIRSTMODEINFO callback, VidPnFunctions_14a2da15-5fde-4701-b3e6-9e60c84f381b.xml, d3dkmddi/pfnAcquireFirstModeInfo, display.dxgk_vidpnsourcemodeset_interface_pfnacquirefirstmodeinfo, pfnAcquireFirstModeInfo, pfnAcquireFirstModeInfo callback function [Display Devices]
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
-	pfnAcquireFirstModeInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNSOURCEMODESET_ACQUIREFIRSTMODEINFO callback function


## -description


The <b>pfnAcquireFirstModeInfo</b> function returns a descriptor of the first mode in a specified VidPN source mode set.


## -parameters




### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param ppFirstVidPnSourceModeInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a> structure. The structure contains a variety of information about the mode, including its ID, type, and rendering format.


## -returns



The <b>pfnAcquireFirstModeInfo</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnSourceModeSet</i> was invalid.

</td>
</tr>
</table>
 




## -remarks



When you have finished using the D3DKMDT_VIDPN_SOURCE_MODE structure, you must release the structure by calling <a href="https://msdn.microsoft.com/614283cc-90bf-44f2-bab2-1aeec5e7de01">pfnReleaseModeInfo</a>.

You can enumerate all the modes that belong to a VidPN source mode set object by calling <b>pfnAcquireFirstModeInfo</b> and then making a sequence of calls to <a href="https://msdn.microsoft.com/d9cb1ff1-c428-46e5-884a-5fc39e16300e">pfnAcquireNextModeInfo</a>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/d9cb1ff1-c428-46e5-884a-5fc39e16300e">pfnAcquireNextModeInfo</a>



<a href="https://msdn.microsoft.com/614283cc-90bf-44f2-bab2-1aeec5e7de01">pfnReleaseModeInfo</a>
 

 

