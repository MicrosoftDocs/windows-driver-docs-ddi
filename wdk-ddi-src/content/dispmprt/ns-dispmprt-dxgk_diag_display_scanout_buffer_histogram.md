---
UID: NS:dispmprt._DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
title: DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM structure provides histogram information for the current buffer being scanned out during diagnostic data collection.
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
req.typenames: DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
 - DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
f1_keywords:
 - _DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
 - dispmprt/_DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
 - DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
 - dispmprt/DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM structure

## -description

The **DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM** structure provides histogram information for the current buffer being scanned out during diagnostic data collection.

## -struct-fields

### -field MinPixelValue

Minimum pixel value in the histogram for the currently scanned out buffer. A value of -1 specifies that no histograms are supported.

### -field MaxPixelValue

Maximum pixel value in the histogram for the currently scanned out buffer.

## -remarks

**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM** is a member of the [**DXGK_DIAG_SCANOUT_BUFFER_CONTENT**](ns-dispmprt-dxgk_diag_scanout_buffer_content.md) structure, which is passed as a member of the [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structure in calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md) during diagnostic data collection.

If the hardware doesn't support CRC calculation on the scanned out pixels and the driver/hardware maintains a histogram of the buffers being scanned out then it should return **MinPixelValue** and **MaxPixelValue** for the current buffer being scanned out. These values should be on the final scanned out pixels including all gamma and any other transformation applied. Since the minimum and maximum values will depend on the gamma values, and the operating system might not know the whole gamma curve being applied, the OS will only use these values for an overall decision of whether the pixels might be black or near black.

## -see-also

[**DXGK_DIAG_SCANOUT_BUFFER_CONTENT**](ns-dispmprt-dxgk_diag_scanout_buffer_content.md)

[**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC**](ne-dispmprt-dxgk_diag_display_scanout_buffer_crc.md)

[**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md)

[**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)
