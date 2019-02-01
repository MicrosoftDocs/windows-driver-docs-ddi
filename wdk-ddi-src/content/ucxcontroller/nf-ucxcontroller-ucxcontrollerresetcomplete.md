---
UID: NF:ucxcontroller.UcxControllerResetComplete
title: UcxControllerResetComplete function (ucxcontroller.h)
description: Informs USB Host Controller Extension (UCX) that the reset operation has competed.
old-location: buses\_ucxcontrollerresetcomplete.htm
tech.root: usbref
ms.assetid: 483147CF-B15D-435C-B5AA-31723D4C2A85
ms.date: 05/07/2018
ms.keywords: UcxControllerResetComplete, UcxControllerResetComplete method [Buses], buses._ucxcontrollerresetcomplete, ucxcontroller/UcxControllerResetComplete
ms.topic: function
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Ucxcontroller.h
api_name:
-	UcxControllerResetComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxControllerResetComplete function


## -description


Informs USB Host Controller Extension (UCX) that the reset operation has competed.


## -parameters




### -param Controller [in]

A handle to the controller object to reset. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>.


### -param UcxControllerResetCompleteInfo

TBD




## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 

 

