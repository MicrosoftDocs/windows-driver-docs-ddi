---
UID: NF:ucxcontroller.UcxControllerSetFailed
title: UcxControllerSetFailed function
author: windows-driver-content
description: Informs USB Host Controller Extension (UCX) that the controller has encountered a critical failure.
old-location: buses\_ucxcontrollersetfailed.htm
old-project: usbref
ms.assetid: 76B7F24C-5376-4DE1-86E7-D2D688B86BCF
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UcxControllerSetFailed, ucxcontroller/UcxControllerSetFailed, UcxControllerSetFailed method [Buses], buses._ucxcontrollersetfailed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Ucxcontroller.h
apiname:
-	UcxControllerSetFailed
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# UcxControllerSetFailed function


## -description


Informs USB Host Controller Extension (UCX) that the controller has encountered a critical failure. 


## -syntax


````
void UcxControllerSetFailed(
  [in] UCXCONTROLLER Controller
);
````


## -parameters




### -param Controller [in]

A handle to the controller object. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>.


## -returns


This method does not return a value.



## -remarks


    The client driver for host controller must call this function if the driver fails D0 entry or the driver has stopped processing transfers to or from an endpoint. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxControllerSetFailed method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

