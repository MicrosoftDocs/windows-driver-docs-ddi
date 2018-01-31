---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEVISIBILITY
title: DXGKDDI_SETVIDPNSOURCEVISIBILITY
author: windows-driver-content
description: The DxgkDdiSetVidPnSourceVisibility function programs the video output codec that is associated with a specified video present source to either start scanning or stop scanning the source's primary surface.
old-location: display\dxgkddisetvidpnsourcevisibility.htm
old-project: display
ms.assetid: c94473b4-b898-456d-944d-8879adea16d1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddisetvidpnsourcevisibility, DxgkDdiSetVidPnSourceVisibility callback function [Display Devices], DxgkDdiSetVidPnSourceVisibility, DXGKDDI_SETVIDPNSOURCEVISIBILITY, DXGKDDI_SETVIDPNSOURCEVISIBILITY, d3dkmddi/DxgkDdiSetVidPnSourceVisibility, DmFunctions_6a3bb1aa-8bc1-4672-8028-ea3299809a37.xml
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
-	DxgkDdiSetVidPnSourceVisibility
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_SETVIDPNSOURCEVISIBILITY callback


## -description


The <i>DxgkDdiSetVidPnSourceVisibility</i> function programs the video output codec that is associated with a specified video present source to either start scanning or stop scanning the source's primary surface.


## -prototype


````
DXGKDDI_SETVIDPNSOURCEVISIBILITY DxgkDdiSetVidPnSourceVisibility;

NTSTATUS APIENTRY DxgkDdiSetVidPnSourceVisibility(
  _In_ const HANDLE                           hAdapter,
  _In_ const DXGKARG_SETVIDPNSOURCEVISIBILITY *pSetVidPnSourceVisibility
)
{ ... }
````


## -parameters




#### - hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


#### - pSetVidPnSourceVisibility [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setvidpnsourcevisibility.md">DXGKARG_SETVIDPNSOURCEVISIBILITY</a> structure that contains function arguments.


## -returns


<i>DxgkDdiSetVidPnSourceVisibility </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.



## -remarks


See requirements on calling this function with multiplane overlays in <a href="https://msdn.microsoft.com/BAD7FD48-905D-4547-8C69-133240B39FA3">Multiplane overlay VidPN presentation</a>.

<i>DxgkDdiSetVidPnSourceVisibility</i> should be made pageable.



## -see-also

<a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SETVIDPNSOURCEVISIBILITY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

