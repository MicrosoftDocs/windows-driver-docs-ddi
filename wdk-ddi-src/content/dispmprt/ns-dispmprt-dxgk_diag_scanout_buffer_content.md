---
UID: NS:dispmprt._DXGK_DIAG_SCANOUT_BUFFER_CONTENT
title: DXGK_DIAG_SCANOUT_BUFFER_CONTENT
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CONTENT structure provides information about the current buffer being scanned out during diagnostic data collection.
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DIAG_SCANOUT_BUFFER_CONTENT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAG_SCANOUT_BUFFER_CONTENT
 - DXGK_DIAG_SCANOUT_BUFFER_CONTENT
f1_keywords:
 - dispmprt/_DXGK_DIAG_SCANOUT_BUFFER_CONTENT
 - dispmprt//DXGK_DIAG_SCANOUT_BUFFER_CONTENT
 - DXGK_DIAG_SCANOUT_BUFFER_CONTENT
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CONTENT structure

## -description

The **DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CONTENT** structure provides information about the current buffer being scanned out during diagnostic data collection.

## -struct-fields

### -field ScanoutBufferCrc

[out] A [**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC**](ns-dispmprt-dxgk_diag_display_scanout_buffer_crc.md) value.

### -field ScanoutBufferHistogram

[out] A [**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM**](ns-dispmprt-dxgk_diag_display_scanout_buffer_histogram.md) structure.

## -remarks

The **DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CONTENT** structure is a member of the [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structure, which is passed in calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md) during diagnostic data collection.

Drivers should use either **ScanoutBufferCrc** or **ScanoutBufferHistogram**, or both **ScanoutBufferCrc** and **ScanoutBufferHistogram**, to report to the operating system about the content of the current buffer being scanned out.

## -see-also

[**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC**](ne-dispmprt-dxgk_diag_display_scanout_buffer_crc.md)

[**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM**](ns-dispmprt-dxgk_diag_display_scanout_buffer_histogram.md)

[**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md)

[**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)
