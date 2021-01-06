---
UID: NC:d3dkmddi.DXGKDDI_COLLECTDBGINFO
title: DXGKDDI_COLLECTDBGINFO (d3dkmddi.h)
description: The DxgkDdiCollectDbgInfo function outputs driver information for a debug report.
old-location: display\dxgkddicollectdbginfo.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_COLLECTDBGINFO callback function"]
ms.keywords: DXGKDDI_COLLECTDBGINFO, DXGKDDI_COLLECTDBGINFO callback, DmFunctions_3b0ed5a8-f56d-4dbd-8426-667ff8f37ee5.xml, DxgkDdiCollectDbgInfo, DxgkDdiCollectDbgInfo callback function [Display Devices], d3dkmddi/DxgkDdiCollectDbgInfo, display.dxgkddicollectdbginfo
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_COLLECTDBGINFO
 - d3dkmddi/DXGKDDI_COLLECTDBGINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiCollectDbgInfo
product:
 - Windows
---

# DXGKDDI_COLLECTDBGINFO callback function


## -description

The <i>DxgkDdiCollectDbgInfo</i> function outputs driver information for a debug report.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pCollectDbgInfo

[in] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_collectdbginfo">DXGKARG_COLLECTDBGINFO</a> structure that describes information for the debug report.

## -returns

<i>DxgkDdiCollectDbgInfo</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | [DxgkDdiCollectDbgInfo]()  successfully output driver information for a debug report; otherwise, the operating system ignored the content in the buffer that the pBuffermember of the [DXGKARG_COLLECTDBGINFO](./ns-d3dkmddi-_dxgkarg_collectdbginfo.md) structure pointed to and added no information from DxgkDdiCollectDbgInfo to the debug report. | 
| **STATUS_NO_MEMORY** | [DxgkDdiCollectDbgInfo]()  could not allocate memory that was required for it to complete. |
| **STATUS_UNSUCCESSFULL** | Another error prevented the driver from collecting valid debug information. |

## -remarks

The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiCollectDbgInfo</i> function whenever the operating system is about to generate a driver-related debug report. <i>DxgkDdiCollectDbgInfo</i> might be called either immediately before Timeout Detection and Recovery (TDR) work (for more information, see <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetfromtimeout">DxgkDdiResetFromTimeout</a>) or immediately before the operating system bug checks. 

The display miniport driver should collect debug information. When <i>DxgkDdiCollectDbgInfo</i> is called, the driver receives a bug-check code in the <b>Reason</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_collectdbginfo">DXGKARG_COLLECTDBGINFO</a> structure that the <i>pCollectDbgInfo</i> parameter points to that indicates the type of information required for the debug report. The driver copies the required debug information to the buffer that the <b>pBuffer</b> member of <b>DXGKARG_COLLECTDBGINFO</b> points to. The <b>BufferSize</b> member of <b>DXGKARG_COLLECTDBGINFO</b> specifies the maximum number of bytes of information that the driver can copy. 

<i>DxgkDdiCollectDbgInfo</i> generally runs at an undefined IRQL. However, if the <b>Reason</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_collectdbginfo">DXGKARG_COLLECTDBGINFO</a> structure that the <i>pCollectDbgInfo</i> parameter points to is set to <a href="/windows-hardware/drivers/debugger/bug-check-code-reference2">VIDEO_TDR_TIMEOUT_DETECTED</a> (to indicate an adapter-wide reset) or <a href="/windows-hardware/drivers/debugger/bug-check-code-reference2">VIDEO_ENGINE_TIMEOUT_DETECTED</a> (available starting with Windows 8 to indicate a reset of one or more nodes within a physical adapter), the driver must ensure that <i>DxgkDdiCollectDbgInfo</i> is pageable, runs at IRQL = <b>PASSIVE_LEVEL</b>, and supports <a href="/windows-hardware/drivers/display/threading-and-synchronization-zero-level">synchronization zero level</a>.

For more information, see <a href="/windows-hardware/drivers/display/tdr-changes-in-windows-8">TDR changes in Windows 8</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_collectdbginfo">DXGKARG_COLLECTDBGINFO</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetfromtimeout">DxgkDdiResetFromTimeout</a>
