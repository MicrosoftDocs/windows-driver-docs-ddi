---
UID: NF:udecxurb.UdecxUrbCompleteWithNtStatus
title: UdecxUrbCompleteWithNtStatus function (udecxurb.h)
description: Completes the URB request with an NTSTATUS code.
old-location: buses\udecxurbcompletewithntstatus.htm
tech.root: usbref
ms.assetid: E1EAA11F-B32F-4551-9788-49BC8A13BB19
ms.date: 05/07/2018
keywords: ["UdecxUrbCompleteWithNtStatus function"]
ms.keywords: UdecxUrbCompleteWithNtStatus, UdecxUrbCompleteWithNtStatus function [Buses], buses.udecxurbcompletewithntstatus, udecxurb/UdecxUrbCompleteWithNtStatus
f1_keywords:
 - "udecxurb/UdecxUrbCompleteWithNtStatus"
 - "UdecxUrbCompleteWithNtStatus"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUrbCompleteWithNtStatus
targetos: Windows
req.typenames: 
---

# UdecxUrbCompleteWithNtStatus function


## -description


Completes the URB request with an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.



## -parameters




### -param Request [in]

A handle to a framework request object that contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> for the transfer.


### -param NtStatus [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a>-typed value that indicates the success or failure of the completed URB request. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

