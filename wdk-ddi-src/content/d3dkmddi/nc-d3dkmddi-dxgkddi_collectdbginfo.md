---
UID: NC:d3dkmddi.DXGKDDI_COLLECTDBGINFO
title: DXGKDDI_COLLECTDBGINFO
author: windows-driver-content
description: The DxgkDdiCollectDbgInfo function outputs driver information for a debug report.
old-location: display\dxgkddicollectdbginfo.htm
old-project: display
ms.assetid: f2f3d8f7-5a54-4830-b8f8-ac2f93096eda
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_COLLECTDBGINFO, DmFunctions_3b0ed5a8-f56d-4dbd-8426-667ff8f37ee5.xml, DxgkDdiCollectDbgInfo, DxgkDdiCollectDbgInfo callback function [Display Devices], d3dkmddi/DxgkDdiCollectDbgInfo, display.dxgkddicollectdbginfo
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiCollectDbgInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_COLLECTDBGINFO callback


## -description


The <i>DxgkDdiCollectDbgInfo</i> function outputs driver information for a debug report.


## -prototype


````
DXGKDDI_COLLECTDBGINFO DxgkDdiCollectDbgInfo;

NTSTATUS APIENTRY DxgkDdiCollectDbgInfo(
  _In_ const HANDLE                 hAdapter,
  _In_ const DXGKARG_COLLECTDBGINFO *pCollectDbgInfo
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pCollectDbgInfo [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_collectdbginfo.md">DXGKARG_COLLECTDBGINFO</a> structure that describes information for the debug report.


## -returns



<i>DxgkDdiCollectDbgInfo</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_collectdbginfo.md">DxgkDdiCollectDbgInfo</a> successfully output driver information for a debug report; otherwise, the operating system ignored the content in the buffer that the <b>pBuffer</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_collectdbginfo.md">DXGKARG_COLLECTDBGINFO</a> structure pointed to and added no information from <i>DxgkDdiCollectDbgInfo</i> to the debug report.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_collectdbginfo.md">DxgkDdiCollectDbgInfo</a> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFULL</b></dt>
</dl>
</td>
<td width="60%">
Another error prevented the driver from collecting valid debug information.

</td>
</tr>
</table>
 




## -remarks



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiCollectDbgInfo</i> function whenever the operating system is about to generate a driver-related debug report. <i>DxgkDdiCollectDbgInfo</i> might be called either immediately before Timeout Detection and Recovery (TDR) work (for more information, see <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetfromtimeout.md">DxgkDdiResetFromTimeout</a>) or immediately before the operating system bug checks. 

The display miniport driver should collect debug information. When <i>DxgkDdiCollectDbgInfo</i> is called, the driver receives a bug-check code in the <b>Reason</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_collectdbginfo.md">DXGKARG_COLLECTDBGINFO</a> structure that the <i>pCollectDbgInfo</i> parameter points to that indicates the type of information required for the debug report. The driver copies the required debug information to the buffer that the <b>pBuffer</b> member of <b>DXGKARG_COLLECTDBGINFO</b> points to. The <b>BufferSize</b> member of <b>DXGKARG_COLLECTDBGINFO</b> specifies the maximum number of bytes of information that the driver can copy. 

<i>DxgkDdiCollectDbgInfo</i> generally runs at an undefined IRQL. However, if the <b>Reason</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_collectdbginfo.md">DXGKARG_COLLECTDBGINFO</a> structure that the <i>pCollectDbgInfo</i> parameter points to is set to <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">VIDEO_TDR_TIMEOUT_DETECTED</a> (to indicate an adapter-wide reset) or <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">VIDEO_ENGINE_TIMEOUT_DETECTED</a> (available starting with Windows 8 to indicate a reset of one or more nodes within a physical adapter), the driver must ensure that <i>DxgkDdiCollectDbgInfo</i> is pageable, runs at IRQL = <b>PASSIVE_LEVEL</b>, and supports <a href="https://msdn.microsoft.com/2baf91e8-fafb-40e2-a24c-cbf04fe45274">synchronization zero level</a>.

For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetfromtimeout.md">DxgkDdiResetFromTimeout</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_collectdbginfo.md">DXGKARG_COLLECTDBGINFO</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_COLLECTDBGINFO callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

