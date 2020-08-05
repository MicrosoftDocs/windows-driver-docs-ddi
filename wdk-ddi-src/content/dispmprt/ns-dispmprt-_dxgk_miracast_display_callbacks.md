---
UID: NS:dispmprt._DXGK_MIRACAST_DISPLAY_CALLBACKS
title: _DXGK_MIRACAST_DISPLAY_CALLBACKS (dispmprt.h)
description: Contains pointers to functions in the Wireless display (Miracast) display callback interface that the display miniport driver can call to send messages and report encode chunk info.
old-location: display\dxgk_miracast_display_callbacks.htm
tech.root: display
ms.assetid: C60F03A1-AD90-43C7-99DF-5EC45151D1F5
ms.date: 05/10/2018
keywords: ["DXGK_MIRACAST_DISPLAY_CALLBACKS structure"]
ms.keywords: "*PDXGK_MIRACAST_DISPLAY_CALLBACKS, DXGK_MIRACAST_DISPLAY_CALLBACKS, DXGK_MIRACAST_DISPLAY_CALLBACKS structure [Display Devices], PDXGK_MIRACAST_DISPLAY_CALLBACKS, PDXGK_MIRACAST_DISPLAY_CALLBACKS structure pointer [Display Devices], _DXGK_MIRACAST_DISPLAY_CALLBACKS, display.dxgk_miracast_display_callbacks, dispmprt/DXGK_MIRACAST_DISPLAY_CALLBACKS, dispmprt/PDXGK_MIRACAST_DISPLAY_CALLBACKS"
f1_keywords:
 - "dispmprt/DXGK_MIRACAST_DISPLAY_CALLBACKS"
 - "DXGK_MIRACAST_DISPLAY_CALLBACKS"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dispmprt.h
api_name:
- DXGK_MIRACAST_DISPLAY_CALLBACKS
targetos: Windows
req.typenames: DXGK_MIRACAST_DISPLAY_CALLBACKS, *PDXGK_MIRACAST_DISPLAY_CALLBACKS
---

# _DXGK_MIRACAST_DISPLAY_CALLBACKS structure


## -description


Contains pointers to functions in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Wireless display (Miracast) display callback interface</a> that the display miniport driver can call to send messages and report encode chunk info.


## -struct-fields




### -field MiracastHandle

A driver-supplied handle to the Miracast display device.


### -field DxgkCbMiracastSendMessage

A pointer to the display port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message">DxgkCbMiracastSendMessage</a> function.


### -field DxgkCbReportChunkInfo

A pointer to the display port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_report_chunk_info">DxgkCbReportChunkInfo</a> function.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_send_message">DxgkCbMiracastSendMessage</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_miracast_report_chunk_info">DxgkCbReportChunkInfo</a>
 

 

