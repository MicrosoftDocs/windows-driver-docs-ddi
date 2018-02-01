---
UID: NC:d3dkmddi.DXGKDDI_SUBMITCOMMAND
title: DXGKDDI_SUBMITCOMMAND
author: windows-driver-content
description: The DxgkDdiSubmitCommand function submits a direct memory access (DMA) buffer to the hardware command execution unit.
old-location: display\dxgkddisubmitcommand.htm
old-project: display
ms.assetid: de1925ab-e444-4cf6-acd9-8fdab26afcec
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddisubmitcommand, DxgkDdiSubmitCommand callback function [Display Devices], DxgkDdiSubmitCommand, DXGKDDI_SUBMITCOMMAND, DXGKDDI_SUBMITCOMMAND, d3dkmddi/DxgkDdiSubmitCommand, DmFunctions_c23ba706-a779-4a0d-9977-1f99cecb5217.xml
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiSubmitCommand
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_SUBMITCOMMAND callback


## -description


The <i>DxgkDdiSubmitCommand</i> function submits a direct memory access (DMA) buffer to the hardware command execution unit.


## -prototype


````
DXGKDDI_SUBMITCOMMAND DxgkDdiSubmitCommand;

NTSTATUS APIENTRY DxgkDdiSubmitCommand(
  _In_ const HANDLE                hAdapter,
  _In_ const DXGKARG_SUBMITCOMMAND *pSubmitCommand
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pSubmitCommand [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_submitcommand.md">DXGKARG_SUBMITCOMMAND</a> structure that describes the DMA buffer that the display miniport driver submits to the hardware command execution unit.


## -returns



      Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.



## -remarks


Because paging operations are considered system operations, they are not associated with a specific application context or graphics context. Therefore, when the submission is for a paging operation, the <i>DxgkDdiSubmitCommand</i> function is called with <b>NULL</b> specified in the <b>hDevice</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_submitcommand.md">DXGKARG_SUBMITCOMMAND</a> structure that the <i>pSubmitCommand</i> parameter points to. 

However, if the architecture of a particular hardware and driver must have a device internally, the driver must internally create the device during adapter initialization and must keep the device internally as the system default device for use in paging operations.

The driver can write the value that is supplied in the <b>SubmissionFenceId</b> member of DXGKARG_SUBMITCOMMAND into the fence command in the ring buffer. For more information about fence commands, see <a href="https://msdn.microsoft.com/0ec8a4eb-c441-47ae-b5de-d86e6065ffd4">Supplying Fence Identifiers</a>.

If the driver returns an error code, the Microsoft DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.
<ol>
<li>0x2</li>
<li>The NTSTATUS error code returned from the failed driver call</li>
<li>A pointer to the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_submitcommand.md">DXGKARG_SUBMITCOMMAND</a> structure</li>
<li>A pointer to an internal scheduler data structure</li>
</ol><i>DxgkDdiSubmitCommand</i> should be made nonpageable because it runs at IRQL = DISPATCH_LEVEL.



## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_submitcommand.md">DXGKARG_SUBMITCOMMAND</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SUBMITCOMMAND callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

