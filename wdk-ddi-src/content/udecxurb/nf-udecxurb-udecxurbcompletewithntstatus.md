---
UID: NF:udecxurb.UdecxUrbCompleteWithNtStatus
title: UdecxUrbCompleteWithNtStatus function
author: windows-driver-content
description: Completes the URB request with an NTSTATUS code.
old-location: buses\udecxurbcompletewithntstatus.htm
old-project: usbref
ms.assetid: E1EAA11F-B32F-4551-9788-49BC8A13BB19
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UdecxUrbCompleteWithNtStatus, UdecxUrbCompleteWithNtStatus function [Buses], buses.udecxurbcompletewithntstatus, udecxurb/UdecxUrbCompleteWithNtStatus
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
-	UdecxUrbCompleteWithNtStatus
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---

# UdecxUrbCompleteWithNtStatus function


## -description


Completes the URB request with an <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.



## -parameters




### -param Request [in]

A handle to a framework request object that contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> for the transfer.


### -param NtStatus [in]

A <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a>-typed value that indicates the success or failure of the completed URB request. 


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

