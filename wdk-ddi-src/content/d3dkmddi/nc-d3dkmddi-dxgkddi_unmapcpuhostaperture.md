---
UID: NC:d3dkmddi.DXGKDDI_UNMAPCPUHOSTAPERTURE
title: DXGKDDI_UNMAPCPUHOSTAPERTURE
author: windows-driver-content
description: DxgkDdiUnmapCpuHostAperture is used to unmap a previously mapped range of the CPU host aperture.
old-location: display\dxgkddiunmapcpuhostaperture.htm
old-project: display
ms.assetid: AFE6B92F-49DB-47F9-90BC-F75B5F37178D
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiunmapcpuhostaperture, DxgkDdiUnmapCpuHostAperture callback function [Display Devices], DxgkDdiUnmapCpuHostAperture, DXGKDDI_UNMAPCPUHOSTAPERTURE, DXGKDDI_UNMAPCPUHOSTAPERTURE, d3dkmddi/DxgkDdiUnmapCpuHostAperture
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiUnmapCpuHostAperture
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_UNMAPCPUHOSTAPERTURE callback


## -description


<b>DxgkDdiUnmapCpuHostAperture</b> is used to unmap a previously mapped range of the CPU host aperture.


## -prototype


````
DXGKDDI_UNMAPCPUHOSTAPERTURE DxgkDdiUnmapCpuHostAperture;

NTSTATUS APIENTRY DxgkDdiUnmapCpuHostAperture(
   HANDLE                       hAdapter,
   DXGKARG_UNMAPCPUHOSTAPERTURE pArgs
)
{ ... }
````


## -parameters




### -param hAdapter

A handle to the display adapter.


### -param pArgs

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_unmapcpuhostaperture.md">DXGKARG_UNMAPCPUHOSTAPERTURE</a> structure that describes the operation.


## -returns




      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_unmapcpuhostaperture.md">DXGKARG_UNMAPCPUHOSTAPERTURE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_UNMAPCPUHOSTAPERTURE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

