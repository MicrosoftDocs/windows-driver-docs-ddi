---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
title: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2
author: windows-driver-content
description: DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 is called to change the overlay configuration being displayed.
old-location: display\dxgkddisetvidpnsourceaddresswithmultiplaneoverlay2.htm
ms.assetid: 7E87D610-6449-47E0-AB6B-9D926B490B45
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2, DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 callback, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 callback function [Display Devices], d3dkmddi/DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2, display.dxgkddisetvidpnsourceaddresswithmultiplaneoverlay2
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
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 callback function


## -description


<b>DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</b> is called to change the overlay configuration being displayed. It must be implemented by Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.


## -parameters




### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.


### -param pSetVidPnSourceAddressWithMultiPlaneOverlay








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn914471">DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2</a> structure that describes the surfaces and display options to present.


## -returns



If this routine succeeds, it returns <b>NTSTATUS_SUCCESS</b>. The driver should always return a success code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn914471">DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2</a>
 

 

