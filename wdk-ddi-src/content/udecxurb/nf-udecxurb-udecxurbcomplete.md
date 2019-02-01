---
UID: NF:udecxurb.UdecxUrbComplete
title: UdecxUrbComplete function (udecxurb.h)
description: Completes the URB request with a USB-specific completion status code.
old-location: buses\udecxurbcomplete.htm
tech.root: usbref
ms.assetid: F0B014F3-AE40-466B-BD9A-0D01DF70DCFF
ms.date: 05/07/2018
ms.keywords: UdecxUrbComplete, UdecxUrbComplete function [Buses], buses.udecxurbcomplete, udecxurb/UdecxUrbComplete
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
-	UdecxUrbComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUrbComplete function


## -description


Completes the URB request with a USB-specific completion status code.



## -parameters




### -param Request [in]

A handle to a framework request object that contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> for the transfer.


### -param UsbdStatus [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff539136">USBD_STATUS</a>-typed value that indicates the success or failure of the completed URB request. 


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

