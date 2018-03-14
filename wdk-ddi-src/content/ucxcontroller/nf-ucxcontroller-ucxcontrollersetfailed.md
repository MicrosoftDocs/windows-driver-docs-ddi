---
UID: NF:ucxcontroller.UcxControllerSetFailed
title: UcxControllerSetFailed function
author: windows-driver-content
description: Informs USB Host Controller Extension (UCX) that the controller has encountered a critical failure.
old-location: buses\_ucxcontrollersetfailed.htm
old-project: usbref
ms.assetid: 76B7F24C-5376-4DE1-86E7-D2D688B86BCF
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcxControllerSetFailed, UcxControllerSetFailed method [Buses], buses._ucxcontrollersetfailed, ucxcontroller/UcxControllerSetFailed
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Ucxcontroller.h
api_name:
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



 

 


