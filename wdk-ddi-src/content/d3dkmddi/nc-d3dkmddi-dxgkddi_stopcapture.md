---
UID: NC:d3dkmddi.DXGKDDI_STOPCAPTURE
title: DXGKDDI_STOPCAPTURE
author: windows-driver-content
description: The DxgkDdiStopCapture function stops the capture hardware from using the given allocation as a capture buffer.
old-location: display\dxgkddistopcapture.htm
old-project: display
ms.assetid: e5d622cc-c550-44cf-8923-5092226066d9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DXGKDDI_STOPCAPTURE, DmFunctions_108ab359-fe5b-46f2-bc1b-f1f91bd5b327.xml, DxgkDdiStopCapture, DxgkDdiStopCapture callback function [Display Devices], d3dkmddi/DxgkDdiStopCapture, display.dxgkddistopcapture
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
-	DxgkDdiStopCapture
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_STOPCAPTURE callback


## -description


The <i>DxgkDdiStopCapture</i> function stops the capture hardware from using the given allocation as a capture buffer.


## -prototype


````
DXGKDDI_STOPCAPTURE DxgkDdiStopCapture;

NTSTATUS APIENTRY DxgkDdiStopCapture(
  _In_ const HANDLE              hAdapter,
  _In_ const DXGKARG_STOPCAPTURE *pStopCapture
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pStopCapture [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_stopcapture.md">DXGKARG_STOPCAPTURE</a> structure that contains the handle to the allocation that is used as a capture buffer.


## -returns



<i>DxgkDdiStopCapture</i> returns STATUS_SUCCESS, or an appropriate error result if the allocation is not successfully stopped.




## -remarks



When a capture buffer is destroyed, the DirectX graphics kernel subsystem calls the <i>DxgkDdiStopCapture</i> function to inform the display miniport driver to stop the capture hardware from using the allocation as the capture buffer. If the capture hardware already stopped using the allocation, the driver should ignore the call.

<i>DxgkDdiStopCapture</i> should be made pageable.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_stopcapture.md">DXGKARG_STOPCAPTURE</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_STOPCAPTURE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

