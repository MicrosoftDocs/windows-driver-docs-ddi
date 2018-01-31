---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_ADDMODE
title: DXGKDDI_VIDPNSOURCEMODESET_ADDMODE
author: windows-driver-content
description: The pfnAddMode function adds a VidPN source mode to a specified VidPN source mode set object.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnaddmode.htm
old-project: display
ms.assetid: 754078c2-f79b-4237-a14c-96903856f3a5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_vidpnsourcemodeset_interface_pfnaddmode, pfnAddMode callback function [Display Devices], pfnAddMode, DXGKDDI_VIDPNSOURCEMODESET_ADDMODE, DXGKDDI_VIDPNSOURCEMODESET_ADDMODE, d3dkmddi/pfnAddMode, VidPnFunctions_4a5d2191-c7d3-4b94-80aa-b6b3c71dfe18.xml
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
-	pfnAddMode
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNSOURCEMODESET_ADDMODE callback


## -description


The <b>pfnAddMode</b> function adds a VidPN source mode to a specified VidPN source mode set object.


## -prototype


````
DXGKDDI_VIDPNSOURCEMODESET_ADDMODE pfnAddMode;

NTSTATUS APIENTRY pfnAddMode(
  _In_ D3DKMDT_HVIDPNSOURCEMODESET     hVidPnSourceModeSet,
  _In_ D3DKMDT_VIDPN_SOURCE_MODE CONST *pVidPnSourceModeInfo
)
{ ... }
````


## -parameters




#### - hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md">pfnAcquireSourceModeSet</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


#### - pVidPnSourceModeInfo [in]

[in] A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure that describes the source mode. The display miniport driver previously obtained this structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>.


## -returns


The <b>pfnAddMode</b> function returns one of the following values:
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


To add a mode to a source mode set, the display miniport driver performs the following steps.

Call <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a> to obtain a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure. The <b>pnfCreateNewModeInfo</b> function allocates the structure, fills in the <b>Id</b> member with a newly generated source mode identifier, and sets the <b>Type</b> member to <b>D3DKMDT_RMT_UNINITIALIZED</b>.

Populate the D3DKMDT_VIDPN_SOURCE_MODE structure (except for the <b>Id</b> member) with information about the mode, including the mode's type and format.

Call <b>pfnAddMode</b> to add the mode to a source mode set. 

The VidPN manager allocates a D3DKMDT_VIDPN_SOURCE_MODE structure when you call <b>pfnCreateNewModeInfo</b>. If you add the mode described by that structure to a source mode set, you do not need to explicitly release the structure; <b>pfnAddMode</b> releases it.

If you obtain a D3DKMDT_VIDPN_SOURCE_MODE structure by calling <b>pfnCreateNewModeInfo</b> and then decide not to add that mode to a source mode set, you must explicity release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 



## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNSOURCEMODESET_ADDMODE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

