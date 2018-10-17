---
UID: NS:d3dkmddi._DXGK_HISTORY_BUFFER
title: "_DXGK_HISTORY_BUFFER"
author: windows-driver-content
description: Specifies a history buffer that stores time stamps that record GPU activity throughout the execution lifetime of a direct memory access (DMA) buffer.
old-location: display\dxgk_history_buffer.htm
ms.assetid: 66088355-A110-4295-81D9-542491E2D6E4
ms.date: 5/10/2018
ms.keywords: DXGK_HISTORY_BUFFER, DXGK_HISTORY_BUFFER structure [Display Devices], _DXGK_HISTORY_BUFFER, d3dkmddi/DXGK_HISTORY_BUFFER, display.dxgk_history_buffer
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_HISTORY_BUFFER
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_HISTORY_BUFFER
---

# _DXGK_HISTORY_BUFFER structure


## -description


Specifies a history buffer that stores time stamps that record GPU activity throughout the execution lifetime of a direct memory access (DMA) buffer.


## -struct-fields




### -field Header

A pointer to  a <a href="https://msdn.microsoft.com/library/windows/hardware/dn439362">DXGK_HISTORY_BUFFER_HEADER</a> structure that contains history buffer header info.


### -field DriverPrivateData

An array that marks the beginning of the optional driver data and timestamp entries. See Remarks for more info.


## -remarks



You can calculate the address of the first time stamp in the history buffer by adding the value of <a href="https://msdn.microsoft.com/library/windows/hardware/dn439362">DXGK_HISTORY_BUFFER_HEADER</a>.<b>PrivateDataSize</b> to the address of <b>DriverPrivateData</b>.

The beginnings of the time stamps should be aligned to a 64-bit boundary.

The first and last time stamps in the <b>DriverPrivateData</b> array must be respectively the start and end times of the DMA buffer. Time stamps that are used to log marker times begin after this end time. This is the case for both formatted and unformatted buffers.

The driver specifies the precision of time stamps with the <a href="https://msdn.microsoft.com/library/windows/hardware/dn439359">DXGKARG_HISTORYBUFFERPRECISION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn439359">DXGKARG_HISTORYBUFFERPRECISION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn439362">DXGK_HISTORY_BUFFER_HEADER</a>
 

 

