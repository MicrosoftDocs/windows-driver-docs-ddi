---
UID: NC:d3dkmddi.DXGKDDI_QUERYADAPTERINFO
title: DXGKDDI_QUERYADAPTERINFO
author: windows-driver-content
description: The DxgkDdiQueryAdapterInfo function retrieves configuration information from the graphics adapter.
old-location: display\dxgkddiqueryadapterinfo.htm
old-project: display
ms.assetid: f2f4c54c-7413-48e5-a165-d71f35642b6c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiqueryadapterinfo, DxgkDdiQueryAdapterInfo callback function [Display Devices], DxgkDdiQueryAdapterInfo, DXGKDDI_QUERYADAPTERINFO, DXGKDDI_QUERYADAPTERINFO, d3dkmddi/DxgkDdiQueryAdapterInfo, DmFunctions_700dcca1-79a6-4d31-953c-00e33c8a404d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
-	DxgkDdiQueryAdapterInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_QUERYADAPTERINFO callback


## -description


The <i>DxgkDdiQueryAdapterInfo</i> function retrieves configuration information from the graphics adapter.


## -prototype


````
DXGKDDI_QUERYADAPTERINFO DxgkDdiQueryAdapterInfo;

NTSTATUS APIENTRY DxgkDdiQueryAdapterInfo(
  _In_ const HANDLE                   hAdapter,
  _In_ const DXGKARG_QUERYADAPTERINFO *pQueryAdapterInfo
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pQueryAdapterInfo [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a> structure that the display miniport driver fills with the configuration information for the graphics adapter.


## -returns


<i>DxgkDdiQueryAdapterInfo</i> returns one of the following values:
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
<i>DxgkDdiQueryAdapterInfo</i> successfully retrieved the configuration information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters that were passed to <i>DxgkDdiQueryAdapterInfo</i> contained errors that prevented it from completing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiQueryAdapterInfo</i> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiQueryAdapterInfo</i> (that is, supplied private data for a query to the display miniport driver). 

</td>
</tr>
</table> 



## -remarks


When the user-mode display driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a> function, a call to the <i>DxgkDdiQueryAdapterInfo</i> function is initiated. <i>DxgkDdiQueryAdapterInfo</i> receives the DXGKQAITYPE_UMDRIVERPRIVATE value in the <b>Type</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a> structure that the <i>pQueryAdapterInfo</i> parameter points to. This function also receives a proprietary buffer in the <b>pOutputData</b> member that it fills with the configuration information that is necessary for the user-mode display driver to identify the adapter. 

If the DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) specifies the DXGKQAITYPE_DRIVERCAPS value in the <b>Type</b> member of DXGKARG_QUERYADAPTERINFO when the subsystem calls <i>DxgkDdiQueryAdapterInfo</i>, the display miniport driver should populate the provided <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure with information that the subsystem can use.

If the DirectX graphics kernel subsystem supplies the DXGKQAITYPE_QUERYSEGMENT value in the <b>Type</b> member of DXGKARG_QUERYADAPTERINFO, the display miniport driver should provide information about the memory segments that it supports. For more information about memory segments, see <a href="https://msdn.microsoft.com/8e4cf1dc-c428-4564-9a16-925e17e6d488">Initializing Use of Memory Segments</a>. 

<i>DxgkDdiQueryAdapterInfo</i> should be made pageable. 



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_QUERYADAPTERINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

