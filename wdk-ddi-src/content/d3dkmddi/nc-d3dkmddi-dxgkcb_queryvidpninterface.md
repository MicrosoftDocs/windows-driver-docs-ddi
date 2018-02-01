---
UID: NC:d3dkmddi.DXGKCB_QUERYVIDPNINTERFACE
title: DXGKCB_QUERYVIDPNINTERFACE
author: windows-driver-content
description: The DxgkCbQueryVidPnInterface function returns a pointer to a DXGK_VIDPN_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter a VidPN object.
old-location: display\dxgkcbqueryvidpninterface.htm
old-project: display
ms.assetid: 649ce7fc-6852-43f3-b944-b2b64fcba874
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbqueryvidpninterface, DxgkCbQueryVidPnInterface callback function [Display Devices], DxgkCbQueryVidPnInterface, DXGKCB_QUERYVIDPNINTERFACE, DXGKCB_QUERYVIDPNINTERFACE, d3dkmddi/DxgkCbQueryVidPnInterface, DpFunctions_0bbf993b-c05b-402b-af4a-cf1a3ec4d4b8.xml
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkCbQueryVidPnInterface
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_QUERYVIDPNINTERFACE callback


## -description


The <b>DxgkCbQueryVidPnInterface</b> function returns a pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter a VidPN object.


## -prototype


````
DXGKCB_QUERYVIDPNINTERFACE DxgkCbQueryVidPnInterface;

NTSTATUS APIENTRY DxgkCbQueryVidPnInterface(
  _In_  const D3DKMDT_HVIDPN               hVidPn,
  _In_  const DXGK_VIDPN_INTERFACE_VERSION VidPnInterfaceVersion,
  _Out_ const DXGK_VIDPN_INTERFACE         **ppVidPnInterface
)
{ ... }
````


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided the display miniport driver with this handle by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a>, or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a>.


### -param VidPnInterfaceVersion [in]

[in] A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_vidpn_interface_version.md">DXGK_VIDPN_INTERFACE_VERSION</a> enumerator that specifies the version of the VidPN interface being requested. Callers must set this parameter to <b>DXGK_VIDPN_INTERFACE_VERSION_V1</b>.


### -param ppVidPnInterface [out]

[out] A pointer to a variable that receives a pointer to the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> structure.


## -returns


<b>DxgkCbQueryVidPnInterface </b>returns one of the following values:
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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value passed to <i>ppVidPnInterface</i> is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The handle passed to <i>hVidPn</i> is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The interface version specified by <i>VidPnInterfaceVersion</i> is not supported.

</td>
</tr>
</table> 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570559">VidPN Target Mode Set Interface</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPN Source Mode Set Interface</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPN Interface</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568435">Monitor Source Mode Set Interface</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570560">VidPN Topology Interface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_QUERYVIDPNINTERFACE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

