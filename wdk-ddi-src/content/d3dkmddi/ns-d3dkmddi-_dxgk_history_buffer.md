---
UID: NS:d3dkmddi._DXGK_HISTORY_BUFFER
title: "_DXGK_HISTORY_BUFFER"
author: windows-driver-content
description: Specifies a history buffer that stores time stamps that record GPU activity throughout the execution lifetime of a direct memory access (DMA) buffer.
old-location: display\dxgk_history_buffer.htm
old-project: display
ms.assetid: 66088355-A110-4295-81D9-542491E2D6E4
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, B, D, DXGK_HISTORY_BUFFER, DXGK_HISTORY_BUFFER structure [Display Devices], E, F, G, H, I, K, O, R, S, T, U, X, Y, _, _DXGK_HISTORY_BUFFER, d3dkmddi/DXGK_HISTORY_BUFFER, display.dxgk_history_buffer"
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
-	DXGK_HISTORY_BUFFER
product: Windows
targetos: Windows
req.typenames: DXGK_HISTORY_BUFFER
---

# _DXGK_HISTORY_BUFFER structure


## -description


Specifies a history buffer that stores time stamps that record GPU activity throughout the execution lifetime of a direct memory access (DMA) buffer.


## -syntax


````
typedef struct _DXGK_HISTORY_BUFFER {
  DXGK_HISTORY_BUFFER_HEADER Header;
  UINT8                      DriverPrivateData[1];
} DXGK_HISTORY_BUFFER;
````


## -struct-fields




### -field Header

A pointer to  a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer_header.md">DXGK_HISTORY_BUFFER_HEADER</a> structure that contains history buffer header info.


### -field DriverPrivateData

An array that marks the beginning of the optional driver data and timestamp entries. See Remarks for more info.


## -remarks



You can calculate the address of the first time stamp in the history buffer by adding the value of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer_header.md">DXGK_HISTORY_BUFFER_HEADER</a>.<b>PrivateDataSize</b> to the address of <b>DriverPrivateData</b>.

The beginnings of the time stamps should be aligned to a 64-bit boundary.

The first and last time stamps in the <b>DriverPrivateData</b> array must be respectively the start and end times of the DMA buffer. Time stamps that are used to log marker times begin after this end time. This is the case for both formatted and unformatted buffers.

The driver specifies the precision of time stamps with the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_historybufferprecision.md">DXGKARG_HISTORYBUFFERPRECISION</a> structure.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer_header.md">DXGK_HISTORY_BUFFER_HEADER</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_historybufferprecision.md">DXGKARG_HISTORYBUFFERPRECISION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_HISTORY_BUFFER structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

