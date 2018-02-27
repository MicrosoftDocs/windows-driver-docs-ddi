---
UID: NC:d3dkmddi.DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT
title: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT
author: windows-driver-content
description: Called by the Microsoft DirectX graphics kernel subsystem to check the details of hardware support for multiplane overlays.
old-location: display\dxgkddicheckmultiplaneoverlaysupport.htm
old-project: display
ms.assetid: 8332DD64-B75E-40A4-9D98-3406187150F2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT, DxgkDdiCheckMultiPlaneOverlaySupport, DxgkDdiCheckMultiPlaneOverlaySupport callback function [Display Devices], d3dkmddi/DxgkDdiCheckMultiPlaneOverlaySupport, display.dxgkddicheckmultiplaneoverlaysupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	DxgkDdiCheckMultiPlaneOverlaySupport
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT callback


## -description


Called by the Microsoft DirectX graphics kernel subsystem to check the details of hardware support for multiplane overlays.


## -prototype


````
DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT DxgkDdiCheckMultiPlaneOverlaySupport;

_Check_return_ NTSTATUS APIENTRY DxgkDdiCheckMultiPlaneOverlaySupport(
  _In_    const HANDLE                                hAdapter,
  _Inout_       DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT *pCheckMultiPlaneOverlaySupport
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pCheckMultiPlaneOverlaySupport [in, out]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport.md">DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT</a> structure that provides details on hardware support for multiplane overlays.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise it returns one of the error codes defined in Ntstatus.h.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport.md">DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

