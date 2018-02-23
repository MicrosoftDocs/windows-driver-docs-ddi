---
UID: NS:d3dkmddi._DXGKARG_FORMATHISTORYBUFFER
title: "_DXGKARG_FORMATHISTORYBUFFER"
author: windows-driver-content
description: Contains info for the display miniport driver to format a history buffer.
old-location: display\dxgkarg_formathistorybuffer.htm
old-project: display
ms.assetid: 40E00234-C22B-4F86-AC5D-197223298FD7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DXGKARG_FORMATHISTORYBUFFER structure [Display Devices], _DXGKARG_FORMATHISTORYBUFFER, display.dxgkarg_formathistorybuffer, DXGKARG_FORMATHISTORYBUFFER, d3dkmddi/DXGKARG_FORMATHISTORYBUFFER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGKARG_FORMATHISTORYBUFFER
product: Windows
targetos: Windows
req.typenames: DXGKARG_FORMATHISTORYBUFFER
---

# _DXGKARG_FORMATHISTORYBUFFER structure


## -description


Contains info for the display miniport driver to format a history buffer.


## -syntax


````
typedef struct _DXGKARG_FORMATHISTORYBUFFER {
  DXGK_HISTORY_BUFFER            *pHistoryBuffer;
  UINT32                         HistoryBufferSize;
  PVOID                          pFormattedBuffer;
  UINT32                         FormattedBufferSize;
  UINT32                         NumTimestamps;
  DXGKARG_HISTORYBUFFERPRECISION Precision;
  UINT32                         Offset;
} DXGKARG_FORMATHISTORYBUFFER;
````


## -struct-fields




### -field pHistoryBuffer

A pointer to the unformatted <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer.md">DXGK_HISTORY_BUFFER</a> history buffer that was populated by the GPU.


### -field HistoryBufferSize

The size, in bytes, of the buffer pointed to by <b>pHistoryBuffer</b>.


### -field pFormattedBuffer

A pointer to a segment of non-paged system memory that the driver uses to store time stamp info that it derives from the provided unformatted history buffer.

The buffer pointed to by <b>pFormattedBuffer</b> should be managed as a large array of time stamps of precision specified by <b>Precision</b>. The buffer should not contain any header info that already exists in the original history buffer.


### -field FormattedBufferSize

The size, in bytes, of the buffer pointed to by <b>pFormattedBuffer</b>. The driver should ensure that it doesn't write data beyond this buffer size.


### -field NumTimestamps

The number of time stamps. On completion of a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_formathistorybuffer.md">DxgkDdiFormatHistoryBuffer</a> function, the driver should set this value to the number of time stamps that are written to the formatted buffer pointed to by <b>pFormattedBuffer</b>.

Note that the number of time stamps that will be in the formatted output buffer won't be known until the driver completes the formatted buffer pointed to by <b>pFormattedBuffer</b>.


### -field Precision

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_historybufferprecision.md">DXGKARG_HISTORYBUFFERPRECISION</a> structure that the driver fills with info on the precision of the time stamps that will be logged to the Event Tracing for Windows (ETW) facility.

The value of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_historybufferprecision.md">DXGKARG_HISTORYBUFFERPRECISION</a>.<b>PrecisionBits</b> member cannot be zero.


### -field Offset

On input to a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_formathistorybuffer.md">DxgkDdiFormatHistoryBuffer</a> function, the value of this member is the offset to the first time stamp at which formatting should start. On completion of the function call, the driver should set the value to zero if it successfully formatted all the time stamps in the history buffer.

If nonzero, the driver could not format all the time stamps in the history buffer without filling the formatted buffer. In this case, the value represents the offset that should be continued from in the next function call.


## -remarks



The driver should obtain time stamp entries and the number of usable time stamps from the header of the provided history buffer. Any additional data that the driver needs for calculations should be stored in private data.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_formathistorybuffer.md">DxgkDdiFormatHistoryBuffer</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_historybufferprecision.md">DXGKARG_HISTORYBUFFERPRECISION</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer.md">DXGK_HISTORY_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_FORMATHISTORYBUFFER structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

