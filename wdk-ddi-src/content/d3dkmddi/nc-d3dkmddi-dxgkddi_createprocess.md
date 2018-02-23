---
UID: NC:d3dkmddi.DXGKDDI_CREATEPROCESS
title: DXGKDDI_CREATEPROCESS
author: windows-driver-content
description: DxgkDdiCreateProcess creates a graphics kernel process object.
old-location: display\dxgkddicreateprocess.htm
old-project: display
ms.assetid: E5AAEEB1-C29E-4AA7-9F8E-2C2DCFADED81
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.dxgkddicreateprocess, DxgkDdiCreateProcess callback function [Display Devices], DxgkDdiCreateProcess, DXGKDDI_CREATEPROCESS, DXGKDDI_CREATEPROCESS, dispmprt/DxgkDdiCreateProcess, d3dkmddi/DxgkDdiCreateProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
-	dispmprt.h
-	d3dkmddi.h
apiname:
-	DxgkDdiCreateProcess
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CREATEPROCESS callback


## -description


<b>DxgkDdiCreateProcess</b> creates a graphics kernel process object.


## -prototype


````
DXGKDDI_CREATEPROCESS DxgkDdiCreateProcess;

NTSTATUS APIENTRY DxgkDdiCreateProcess(
  _In_    const HANDLE                hAdapter,
  _Inout_       DXGKARG_CREATEPROCESS *pArgs
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to the display adapter.


### -param pArgs [in, out]

The <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createprocess.md">DXGKARG_CREATEPROCESS</a> structure that describes the operation.


## -returns




      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.




## -remarks



During process creation the kernel mode driver is allowed to call the <b>DxgkCbReserveVirtualAddressRange</b> callback. At this point the graphics processing unit (GPU) virtual address space for the process is free and the driver has the opportunity to reserve virtual address space for its needs.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createprocess.md">DXGKARG_CREATEPROCESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CREATEPROCESS callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

