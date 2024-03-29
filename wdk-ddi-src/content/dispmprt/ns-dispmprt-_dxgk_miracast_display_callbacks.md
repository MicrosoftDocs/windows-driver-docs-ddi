---
UID: NS:dispmprt._DXGK_MIRACAST_DISPLAY_CALLBACKS
title: DXGK_MIRACAST_DISPLAY_CALLBACKS (dispmprt.h)
description: Contains pointers to functions in the Wireless display (Miracast) display callback interface that the display miniport driver can call to send messages and report encode chunk info.
old-location: display\dxgk_miracast_display_callbacks.htm
tech.root: display
ms.date: 11/19/2021
keywords: ["DXGK_MIRACAST_DISPLAY_CALLBACKS structure"]
ms.keywords: "*PDXGK_MIRACAST_DISPLAY_CALLBACKS, DXGK_MIRACAST_DISPLAY_CALLBACKS, DXGK_MIRACAST_DISPLAY_CALLBACKS structure [Display Devices], PDXGK_MIRACAST_DISPLAY_CALLBACKS, PDXGK_MIRACAST_DISPLAY_CALLBACKS structure pointer [Display Devices], _DXGK_MIRACAST_DISPLAY_CALLBACKS, display.dxgk_miracast_display_callbacks, dispmprt/DXGK_MIRACAST_DISPLAY_CALLBACKS, dispmprt/PDXGK_MIRACAST_DISPLAY_CALLBACKS"
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
targetos: Windows
req.typenames: DXGK_MIRACAST_DISPLAY_CALLBACKS, *PDXGK_MIRACAST_DISPLAY_CALLBACKS
f1_keywords:
 - _DXGK_MIRACAST_DISPLAY_CALLBACKS
 - dispmprt/_DXGK_MIRACAST_DISPLAY_CALLBACKS
 - PDXGK_MIRACAST_DISPLAY_CALLBACKS
 - dispmprt/PDXGK_MIRACAST_DISPLAY_CALLBACKS
 - DXGK_MIRACAST_DISPLAY_CALLBACKS
 - dispmprt/DXGK_MIRACAST_DISPLAY_CALLBACKS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dispmprt.h
api_name:
 - _DXGK_MIRACAST_DISPLAY_CALLBACKS
 - PDXGK_MIRACAST_DISPLAY_CALLBACKS
 - DXGK_MIRACAST_DISPLAY_CALLBACKS
---

# DXGK_MIRACAST_DISPLAY_CALLBACKS structure

## -description

The **DXGK_MIRACAST_DISPLAY_CALLBACKS** structure contains pointers to functions that define the wireless display (Miracast) callback interface that the display miniport driver can call to send messages and report encode chunk info.

## -struct-fields

### -field MiracastHandle

A driver-supplied handle to the Miracast display device.

### -field DxgkCbMiracastSendMessage

A pointer to the display port driver's [**DxgkCbMiracastSendMessage**](nc-dispmprt-dxgkcb_miracast_send_message.md) function.

### -field DxgkCbReportChunkInfo

A pointer to the display port driver's [**DxgkCbReportChunkInfo**](nc-dispmprt-dxgkcb_miracast_report_chunk_info.md) function.
