---
UID: NC:d3dkmddi.DXGKDDI_MAPCPUHOSTAPERTURE
title: DXGKDDI_MAPCPUHOSTAPERTURE
author: windows-driver-content
description: DxgkDdiMapCpuHostAperture is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU.
old-location: display\dxgkddimapcpuhostaperture.htm
old-project: display
ms.assetid: 78729B9A-A9FA-4D1E-8D30-3FFD61B1A7D3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_MAPCPUHOSTAPERTURE, DxgkDdiMapCpuHostAperture, DxgkDdiMapCpuHostAperture callback function [Display Devices], d3dkmddi/DxgkDdiMapCpuHostAperture, display.dxgkddimapcpuhostaperture
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiMapCpuHostAperture
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MAPCPUHOSTAPERTURE callback


## -description


<b>DxgkDdiMapCpuHostAperture</b> is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU.


## -parameters




### -param hAdapter [in]

A handle to the display adapter.


### -param pArgs








#### - Map [in]

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn906822">DXGKARG_MAPCPUHOSTAPERTURE</a> structure that describes the operation.


## -returns




      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.



