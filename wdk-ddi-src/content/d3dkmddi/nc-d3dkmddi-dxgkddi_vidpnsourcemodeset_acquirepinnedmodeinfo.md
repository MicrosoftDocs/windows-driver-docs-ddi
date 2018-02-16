---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO
title: DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO
author: windows-driver-content
description: The pfnAcquirePinnedModeInfo function returns a descriptor of the pinned mode in a specified VidPN source mode set.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnacquirepinnedmodeinfo.htm
old-project: display
ms.assetid: e757852b-ee68-4b07-83c8-9dfd089d1ab7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpnsourcemodeset_interface_pfnacquirepinnedmodeinfo, pfnAcquirePinnedModeInfo callback function [Display Devices], pfnAcquirePinnedModeInfo, DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO, DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO, d3dkmddi/pfnAcquirePinnedModeInfo, VidPnFunctions_552ed18a-24d2-4a92-85fa-3af6aa4733dc.xml
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
-	pfnAcquirePinnedModeInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO callback


## -description


The <b>pfnAcquirePinnedModeInfo</b> function returns a descriptor of the pinned mode in a specified VidPN source mode set.


## -prototype


````
DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO pfnAcquirePinnedModeInfo;

NTSTATUS APIENTRY pfnAcquirePinnedModeInfo(
  _In_  const D3DKMDT_HVIDPNSOURCEMODESET hVidPnSourceModeSet,
  _Out_ const D3DKMDT_VIDPN_SOURCE_MODE   **ppPinnedVidPnSourceModeInfo
)
{ ... }
````


## -parameters




### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param ppPinnedVidPnSourceModeInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure. The structure contains a variety of information about the pinned mode, including its ID, type, and rendering format. If the source mode set identified by <i>hVidPnSourceModeSet</i> has no pinned mode, then this variable receives a <b>NULL</b> pointer.


## -returns



The <b>pfnAcquirePinnedModeInfo</b> function returns one of the following values:

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
The function succeeded by doing one of the following:

Setting <i>ppPinnedVidPnSourceModeInfo</i> to the address of D3DKMDT_VIDPN_SOURCE_MODE structure that describes the pinned mode.

Setting <i>ppPinnedVidPnSourceModeInfo</i> to <b>NULL</b> to indicate that the source mode set has no pinned mode. 

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



When you have finished using the D3DKMDT_VIDPN_SOURCE_MODE structure, you must release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_pinmode.md">pfnPinMode</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

