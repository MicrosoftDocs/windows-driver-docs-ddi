---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
title: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
author: windows-driver-content
description: DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 is called to change the overlay configuration being displayed.
old-location: display\dxgkddisetvidpnsourceaddresswithmultiplaneoverlay2.htm
old-project: display
ms.assetid: 7E87D610-6449-47E0-AB6B-9D926B490B45
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 callback function [Display Devices], d3dkmddi/DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2, display.dxgkddisetvidpnsourceaddresswithmultiplaneoverlay2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: INTERRUPT_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 callback


## -description


<b>DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</b> is called to change the overlay configuration being displayed. It must be implemented by Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.


## -prototype


````
DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2;

NTSTATUS APIENTRY DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2(
  _In_ const HANDLE                                              hAdapter,
  _In_ const DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 *pData
)
{ ... }
````


## -parameters




### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.


### -param pSetVidPnSourceAddressWithMultiPlaneOverlay








#### - pData [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay2.md">DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2</a> structure that describes the surfaces and display options to present.


## -returns



If this routine succeeds, it returns <b>NTSTATUS_SUCCESS</b>. The driver should always return a success code.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay2.md">DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

