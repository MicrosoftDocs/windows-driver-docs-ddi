---
UID: NC:d3dkmddi.DXGKDDI_QUERYENGINESTATUS
title: DXGKDDI_QUERYENGINESTATUS
author: windows-driver-content
description: The display port driver's GPU scheduler calls this function to determine the progress of a node within an active physical display adapter (engine).
old-location: display\dxgkddiqueryenginestatus.htm
old-project: display
ms.assetid: 87c99fcb-d25a-41b1-a1f3-9cf9ab7b141e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiqueryenginestatus, DxgkDdiQueryEngineStatus callback function [Display Devices], DxgkDdiQueryEngineStatus, DXGKDDI_QUERYENGINESTATUS, DXGKDDI_QUERYENGINESTATUS, d3dkmddi/DxgkDdiQueryEngineStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmddi.h
apiname:
-	DxgkDdiQueryEngineStatus
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_QUERYENGINESTATUS callback


## -description


The display port driver's GPU scheduler calls this function to determine the progress of a node within an active physical display adapter (engine).


## -prototype


````
DXGKDDI_QUERYENGINESTATUS DxgkDdiQueryEngineStatus;

NTSTATUS APIENTRY DxgkDdiQueryEngineStatus(
  _In_    const HANDLE                    hAdapter,
  _Inout_       DXGKARG_QUERYENGINESTATUS *pQueryEngineStatus
)
{ ... }
````


## -parameters




#### - hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


#### - pQueryEngineStatus [in, out]

A pointer to a   <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryenginestatus.md">DXGKARG_QUERYENGINESTATUS</a> structure that specifies a node and physical adapter that are to be queried for progress, and that supplies a value for the progress.


## -returns


Returns STATUS_SUCCESS if the function succeeds. Otherwise, this function returns one of the error codes defined in Ntstatus.h.



## -remarks


 This function should be made pageable, and it should always succeed.

The operating system guarantees that this function follows the first level synchronization mode as defined in <a href="https://msdn.microsoft.com/9fce6a18-2a66-4518-b05b-e85bdaa3951f">Threading and Synchronization First Level</a>.

For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryenginestatus.md">DXGKARG_QUERYENGINESTATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_QUERYENGINESTATUS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

