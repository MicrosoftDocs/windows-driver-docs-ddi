---
UID: NC:dispmprt.DXGKCB_MIRACAST_REPORT_CHUNK_INFO
title: DXGKCB_MIRACAST_REPORT_CHUNK_INFO (dispmprt.h)
description: Called by the display miniport driver to report info about an encode chunk.
old-location: display\dxgkcbreportchunkinfo.htm
tech.root: display
ms.assetid: 94A99749-EF80-4593-B03C-54A7AA2BDFC8
ms.date: 05/10/2018
keywords: ["DXGKCB_MIRACAST_REPORT_CHUNK_INFO callback function"]
ms.keywords: DXGKCB_MIRACAST_REPORT_CHUNK_INFO, DXGKCB_MIRACAST_REPORT_CHUNK_INFO callback, DxgkCbReportChunkInfo, DxgkCbReportChunkInfo callback function [Display Devices], display.dxgkcbreportchunkinfo, dispmprt/DxgkCbReportChunkInfo
f1_keywords:
 - "dispmprt/DxgkCbReportChunkInfo"
 - "DxgkCbReportChunkInfo"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: Can be called at any IRQL level.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Dispmprt.h
api_name:
- DxgkCbReportChunkInfo
targetos: Windows
req.typenames: 
---

# DXGKCB_MIRACAST_REPORT_CHUNK_INFO callback function


## -description


Called by the display miniport driver to report info about an encode chunk.


## -parameters




### -param MiracastHandle 
[in]
A driver-supplied handle to the Miracast display device. This handle was originally passed in the <b>MiracastHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_miracast_display_callbacks">DXGK_MIRACAST_DISPLAY_CALLBACKS</a> structure in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a> function.


### -param pChunkInfo 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-dxgk_miracast_chunk_info">DXGK_MIRACAST_CHUNK_INFO</a> structure that contains chunk information that is to be reported by the display miniport driver.


### -param pPrivateDriverData 
[in]
Reserved for system use. Must be set to <b>NULL</b>.


### -param PrivateDataDriverSize 
[in]
Reserved for system use. Must be set to zero.


## -returns



Returns <b>STATUS_SUCCESS</b> if it successfully delivers the message. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



The display miniport driver  calls this function when it wants to report chunk info to the operating system but won't create a chunk packet that will be queued in kernel mode and retrieved by the user-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_get_next_chunk_data">GetNextChunkData</a> function.  This call only logs Event Tracing for Windows (ETW) events and takes no other action.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-dxgk_miracast_chunk_info">DXGK_MIRACAST_CHUNK_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_miracast_display_callbacks">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_create_context">DxgkDdiMiracastCreateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_get_next_chunk_data">GetNextChunkData</a>
 

 

