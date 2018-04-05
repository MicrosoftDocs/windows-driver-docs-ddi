---
UID: NE:sercx._SERCX_STATUS
title: "_SERCX_STATUS"
author: windows-driver-content
description: The SERCX_STATUS enumeration indicates the status of a serial receive or transmit operation.
old-location: serports\sercx_status.htm
old-project: serports
ms.assetid: 7EF129C7-25C3-49D2-8FC5-FFA1C4E77935
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERCX_STATUS, 1/SERCX_STATUS, 1/SerCxStatusCancelled, 1/SerCxStatusSuccess, 1/SerCxStatusTimeout, SERCX_STATUS, SERCX_STATUS enumeration [Serial Ports], SerCxStatusCancelled, SerCxStatusSuccess, SerCxStatusTimeout, _SERCX_STATUS, serports.sercx_status"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1.0\Sercx.h
api_name:
-	SERCX_STATUS
product:
- Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# _SERCX_STATUS enumeration


## -description


The <b>SERCX_STATUS</b> enumeration indicates the status of a serial receive or transmit operation.


## -enum-fields




### -field SerCxStatusSuccess

The operation is proceeding successfully.


### -field SerCxStatusCancelled

The operation was canceled.


### -field SerCxStatusTimeout

The operation timed out. This enumeration value applies only to read interval time-outs for receive operations. For more information, see the description of the <b>ReadIntervalTimeout</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406713">SerCxProgressReceive</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh406715">SerCxProgressTransmit</a> methods have parameters that are <b>SERCX_STATUS</b> enumeration values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406713">SerCxProgressReceive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406715">SerCxProgressTransmit</a>
 

 

