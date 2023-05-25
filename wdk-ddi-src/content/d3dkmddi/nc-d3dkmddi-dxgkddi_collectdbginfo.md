---
UID: NC:d3dkmddi.DXGKDDI_COLLECTDBGINFO
title: DXGKDDI_COLLECTDBGINFO (d3dkmddi.h)
description: Learn more about the DXGKDDI_COLLECTDBGINFO callback function.
ms.date: 05/25/2023
keywords: ["DXGKDDI_COLLECTDBGINFO callback function"]
ms.keywords: DXGKDDI_COLLECTDBGINFO, DXGKDDI_COLLECTDBGINFO callback, DmFunctions_3b0ed5a8-f56d-4dbd-8426-667ff8f37ee5.xml, DxgkDdiCollectDbgInfo, DxgkDdiCollectDbgInfo callback function [Display Devices], d3dkmddi/DxgkDdiCollectDbgInfo, display.dxgkddicollectdbginfo
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - DXGKDDI_COLLECTDBGINFO
product:
 - Windows
---

# DXGKDDI_COLLECTDBGINFO callback function

## -description

The **DxgkDdiCollectDbgInfo** function outputs driver information for a debug report.

## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport (KMD) previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md).

### -param pCollectDbgInfo [in/out]

A pointer to a [**DXGKARG_COLLECTDBGINFO**](ns-d3dkmddi-_dxgkarg_collectdbginfo.md) structure that contains information for the debug report.

## -returns

**DxgkDdiCollectDbgInfo** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_SUCCESS** | **DxgkDdiCollectDbgInfo** successfully output driver information for a debug report; OR, the OS ignored the content in the buffer that [**pBuffer**](ns-d3dkmddi-_dxgkarg_collectdbginfo.md) points to and didn't add information from **DxgkDdiCollectDbgInfo** to the debug report. |
| **STATUS_NO_MEMORY** | **DxgkDdiCollectDbgInfo** couldn't allocate memory that was required for it to complete. |
| **STATUS_UNSUCCESSFUL** | Another error prevented the driver from collecting valid debug information. |

## -remarks

*Dxgkrnl* calls KMD's **DxgkDdiCollectDbgInfo** function whenever the OS is about to generate a driver-related debug report. **DxgkDdiCollectDbgInfo** might be called either immediately before [Timeout Detection and Recovery (TDR) work](/windows-hardware/drivers/display/tdr-changes-in-windows-8) or immediately before the OS bug checks. While **DxgkDdiCollectDbgInfo** should return as quickly as possible, there is no system-defined maximum amount of time that the driver can spend in this function.

KMD should collect debug information. When **DxgkDdiCollectDbgInfo** is called, the driver receives a bug-check code in [**pCollectDbgInfo->Reason**](ns-d3dkmddi-_dxgkarg_collectdbginfo.md) that indicates the type of information required for the debug report. The driver copies the required debug information into the buffer that **pCollectDbgInfo->pBuffer** points to. The maximum number of bytes of information that the driver can copy is specified by **pCollectDbgInfo->BufferSize**.

**DxgkDdiCollectDbgInfo** generally runs at an undefined IRQL. However, if **pCollectDbgInfo->Reason** is set to [**VIDEO_TDR_TIMEOUT_DETECTED**](/windows-hardware/drivers/debugger/bug-check-0x117---video-tdr-timeout-detected) (to indicate an adapter-wide reset) or [**VIDEO_ENGINE_TIMEOUT_DETECTED**](/windows-hardware/drivers/debugger/bug-check-0x141---video-engine-timeout-detected) (available starting with Windows 8 to indicate a reset of one or more nodes within a physical adapter), the driver must ensure that **DxgkDdiCollectDbgInfo** is pageable, runs at IRQL = **PASSIVE_LEVEL**, and supports [synchronization zero level](/windows-hardware/drivers/display/threading-and-synchronization-zero-level).

## -see-also

[**DXGKARG_COLLECTDBGINFO**](ns-d3dkmddi-_dxgkarg_collectdbginfo.md)

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiResetFromTimeout**](nc-d3dkmddi-dxgkddi_resetfromtimeout.md)
