---
UID: NE:dispmprt._DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC
title: DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC enum provides CRC information for the current buffer being scanned out during diagnostic data collection.
tech.root: display
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC
 - DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC
f1_keywords:
 - dispmprt/_DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC
 - dispmprt/DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC enumeration

## -description

The **DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC** enum provides CRC information for the current buffer being scanned out during diagnostic data collection.

## -enum-fields

### -field DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC_BLACK

Driver should return this value if based on the calculated CRC of the scanned out pixels they appear as all black.

### -field DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC_NON_BLACK

Driver should return this value if based on the calculated CRC of the scanned out pixels they do not appear as all black.

### -field DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC_ERROR

Driver should return this value if there was an error encountered while calculating the CRC or reference CRC was missing.

### -field DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC_UNKNOWN

Driver should return this value if the hardware doesn't support calculating the CRC on scanned out pixels.

## -remarks

The **DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CRC** enum is a member of the [**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CONTENT**](ns-dispmprt-dxgk_diag_display_scanout_buffer_content.md) structure, which is passed as a member of the [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structure in calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md) during diagnostic data collection.

If the hardware supports performing a CRC calculation on the final scanned out pixels then the driver should enable it. If the driver would need a reference black CRC to check against the current CRC then it should always cache the reference one. If the reference CRC depends on the current mode then it should change the reference on mode changes.

## -see-also

[**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_CONTENT**](ns-dispmprt-dxgk_diag_display_scanout_buffer_content.md)

[**DXGK_DIAG_DISPLAY_SCANOUT_BUFFER_HISTOGRAM**](ns-dispmprt-dxgk_diag_display_scanout_buffer_histogram.md)

[**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md)

[**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)