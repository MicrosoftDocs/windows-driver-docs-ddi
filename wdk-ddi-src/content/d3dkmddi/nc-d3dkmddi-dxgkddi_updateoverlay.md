---
UID: NC:d3dkmddi.DXGKDDI_UPDATEOVERLAY
title: DXGKDDI_UPDATEOVERLAY
author: windows-driver-content
description: The DxgkDdiUpdateOverlay function modifies the overlay hardware.
old-location: display\dxgkddiupdateoverlay.htm
old-project: display
ms.assetid: b131dbb9-1e11-4d04-97cb-e15ec2b025c7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiupdateoverlay, DxgkDdiUpdateOverlay callback function [Display Devices], DxgkDdiUpdateOverlay, DXGKDDI_UPDATEOVERLAY, DXGKDDI_UPDATEOVERLAY, d3dkmddi/DxgkDdiUpdateOverlay, DmFunctions_cc73fb5c-c4b9-476a-9227-fe2d15e288ea.xml
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
-	DxgkDdiUpdateOverlay
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_UPDATEOVERLAY callback


## -description


The <i>DxgkDdiUpdateOverlay</i> function modifies the overlay hardware.


## -prototype


````
DXGKDDI_UPDATEOVERLAY DxgkDdiUpdateOverlay;

NTSTATUS APIENTRY DxgkDdiUpdateOverlay(
  _In_ const HANDLE                hOverlay,
  _In_ const DXGKARG_UPDATEOVERLAY *pUpdateOverlay
)
{ ... }
````


## -parameters




### -param hOverlay [in]

[in] A handle to the overlay to modify. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hOverlay</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createoverlay.md">DXGKARG_CREATEOVERLAY</a> structure that <i>pCreateOverlay</i> points to. 


### -param pUpdateOverlay [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_updateoverlay.md">DXGKARG_UPDATEOVERLAY</a> structure that describes how to modify the overlay hardware.


## -returns


<i>DxgkDdiUpdateOverlay</i> returns one of the following values:
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
<i>DxgkDdiUpdateOverlay</i> successfully modified the overlay.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters that were passed to <i>DxgkDdiUpdateOverlay</i> contained errors that prevented it from completing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiUpdateOverlay</i> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiUpdateOverlay</i> could not complete because insufficient bandwidth was available or the requested overlay hardware could not complete the task.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiUpdateOverlay</i>. 

</td>
</tr>
</table> 



## -remarks


<i>DxgkDdiUpdateOverlay</i> should be made pageable.



## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createoverlay.md">DXGKARG_CREATEOVERLAY</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_updateoverlay.md">DXGKARG_UPDATEOVERLAY</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_UPDATEOVERLAY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

