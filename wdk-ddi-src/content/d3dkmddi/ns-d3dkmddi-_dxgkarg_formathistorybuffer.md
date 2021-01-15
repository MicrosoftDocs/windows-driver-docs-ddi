---
UID: NS:d3dkmddi._DXGKARG_FORMATHISTORYBUFFER
title: _DXGKARG_FORMATHISTORYBUFFER (d3dkmddi.h)
description: Contains info for the display miniport driver to format a history buffer.
old-location: display\dxgkarg_formathistorybuffer.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_FORMATHISTORYBUFFER structure"]
ms.keywords: DXGKARG_FORMATHISTORYBUFFER, DXGKARG_FORMATHISTORYBUFFER structure [Display Devices], _DXGKARG_FORMATHISTORYBUFFER, d3dkmddi/DXGKARG_FORMATHISTORYBUFFER, display.dxgkarg_formathistorybuffer
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
tech.root: display
req.typenames: DXGKARG_FORMATHISTORYBUFFER
f1_keywords:
 - _DXGKARG_FORMATHISTORYBUFFER
 - d3dkmddi/_DXGKARG_FORMATHISTORYBUFFER
 - DXGKARG_FORMATHISTORYBUFFER
 - d3dkmddi/DXGKARG_FORMATHISTORYBUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGKARG_FORMATHISTORYBUFFER
 - DXGKARG_FORMATHISTORYBUFFER
---

# _DXGKARG_FORMATHISTORYBUFFER structure


## -description

Contains info for the display miniport driver to format a history buffer.

## -struct-fields

### -field pHistoryBuffer

A pointer to the unformatted <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_history_buffer">DXGK_HISTORY_BUFFER</a> history buffer that was populated by the GPU.

### -field HistoryBufferSize

The size, in bytes, of the buffer pointed to by <b>pHistoryBuffer</b>.

### -field pFormattedBuffer

A pointer to a segment of non-paged system memory that the driver uses to store time stamp info that it derives from the provided unformatted history buffer.

The buffer pointed to by <b>pFormattedBuffer</b> should be managed as a large array of time stamps of precision specified by <b>Precision</b>. The buffer should not contain any header info that already exists in the original history buffer.

### -field FormattedBufferSize

The size, in bytes, of the buffer pointed to by <b>pFormattedBuffer</b>. The driver should ensure that it doesn't write data beyond this buffer size.

### -field NumTimestamps

The number of time stamps. On completion of a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_formathistorybuffer">DxgkDdiFormatHistoryBuffer</a> function, the driver should set this value to the number of time stamps that are written to the formatted buffer pointed to by <b>pFormattedBuffer</b>.

Note that the number of time stamps that will be in the formatted output buffer won't be known until the driver completes the formatted buffer pointed to by <b>pFormattedBuffer</b>.

### -field Precision

A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_historybufferprecision">DXGKARG_HISTORYBUFFERPRECISION</a> structure that the driver fills with info on the precision of the time stamps that will be logged to the Event Tracing for Windows (ETW) facility.

The value of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_historybufferprecision">DXGKARG_HISTORYBUFFERPRECISION</a>.<b>PrecisionBits</b> member cannot be zero.

### -field Offset

On input to a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_formathistorybuffer">DxgkDdiFormatHistoryBuffer</a> function, the value of this member is the offset to the first time stamp at which formatting should start. On completion of the function call, the driver should set the value to zero if it successfully formatted all the time stamps in the history buffer.

If nonzero, the driver could not format all the time stamps in the history buffer without filling the formatted buffer. In this case, the value represents the offset that should be continued from in the next function call.

## -remarks

The driver should obtain time stamp entries and the number of usable time stamps from the header of the provided history buffer. Any additional data that the driver needs for calculations should be stored in private data.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_historybufferprecision">DXGKARG_HISTORYBUFFERPRECISION</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_history_buffer">DXGK_HISTORY_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_formathistorybuffer">DxgkDdiFormatHistoryBuffer</a>

