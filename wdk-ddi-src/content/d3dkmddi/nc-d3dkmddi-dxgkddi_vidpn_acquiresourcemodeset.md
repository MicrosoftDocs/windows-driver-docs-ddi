---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ACQUIRESOURCEMODESET
title: DXGKDDI_VIDPN_ACQUIRESOURCEMODESET
author: windows-driver-content
description: The pfnAcquireSourceModeSet function returns a handle to a particular source mode set object that is contained by a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfnacquiresourcemodeset.htm
old-project: display
ms.assetid: cf19f468-86c1-4cc9-8945-e23f73a85c91
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_VIDPN_ACQUIRESOURCEMODESET, VidPnFunctions_1ef2f7d1-cdea-4b0d-a8b5-76b5013afba3.xml, d3dkmddi/pfnAcquireSourceModeSet, display.dxgk_vidpn_interface_pfnacquiresourcemodeset, pfnAcquireSourceModeSet, pfnAcquireSourceModeSet callback function [Display Devices]
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
-	pfnAcquireSourceModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPN_ACQUIRESOURCEMODESET callback


## -description


The <b>pfnAcquireSourceModeSet</b> function returns a handle to a particular source mode set object that is contained by a specified VidPN object.


## -prototype


````
DXGKDDI_VIDPN_ACQUIRESOURCEMODESET pfnAcquireSourceModeSet;

NTSTATUS APIENTRY pfnAcquireSourceModeSet(
  _In_  const D3DKMDT_HVIDPN                    hVidPn,
  _In_  const D3DDDI_VIDEO_PRESENT_SOURCE_ID    VidPnSourceId,
  _Out_       D3DKMDT_HVIDPNSOURCEMODESET       *phVidPnSourceModeSet,
  _Out_ const DXGK_VIDPNSOURCEMODESET_INTERFACE **ppVidPnSourceModeSetInterface
)
{ ... }
````


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a>, or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>.


### -param VidPnSourceId [in]

[in] An integer that identifies one of the video present sources associated with the VidPN object.


### -param phVidPnSourceModeSet [out]

[out] A pointer to a variable that receives a handle to the requested source mode set object.


### -param ppVidPnSourceModeSetInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface.md">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the source mode set object.


## -returns



The <b>pfnAcquireSourceModeSet</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPn</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The identifier supplied in <i>VidPnSourceId</i> was invalid.

</td>
</tr>
</table>
 




## -remarks



VidPN source identifiers are assigned by the operating system. <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

When you have finished using the source mode set object handle, you must release the handle by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset.md">pfnReleaseSourceModeSet</a>. Source mode set objects are reference counted, so if you acquire a handle several times, you must release it that same number of times.

The lifetime of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface.md">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> structure returned in <i>ppVidPnSourceModeSetInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can switch to newer implementations at run time without breaking clients of the interface.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>. 




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset.md">pfnCreateNewSourceModeSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPN Source Mode Set Interface</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset.md">pfnReleaseTargetModeSet</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset.md">pfnAssignTargetModeSet</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPN_ACQUIRESOURCEMODESET callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

