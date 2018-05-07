---
UID: NF:udecxurb.UdecxUrbSetBytesCompleted
title: UdecxUrbSetBytesCompleted function
author: windows-driver-content
description: Sets the number of bytes transferred for the URB contained within a framework request object.
old-location: buses\udecxurbsetbytescompleted.htm
old-project: usbref
ms.assetid: 86C320B0-F679-4A8E-9015-D2BD8059A6CD
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: UdecxUrbSetBytesCompleted, UdecxUrbSetBytesCompleted function [Buses], buses.udecxurbsetbytescompleted, udecxurb/UdecxUrbSetBytesCompleted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxurb.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUrbSetBytesCompleted
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUrbSetBytesCompleted function


## -description


Sets the number of bytes transferred for the URB contained within a framework  request object.



## -parameters




### -param Request [in]

A handle to a framework request object that contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> for the transfer.


### -param BytesCompleted

TBD




#### - Length [in]

The number of transferred bytes to set in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>. This value must not be greater than the transfer buffer length.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

