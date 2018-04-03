---
UID: NF:ucxcontroller.UcxControllerNeedsReset
title: UcxControllerNeedsReset function
author: windows-driver-content
description: Initiates a non-Plug and Play (PnP) controller reset operation by queuing an event into the controller reset state machine.
old-location: buses\_ucxcontrollerneedsreset.htm
old-project: usbref
ms.assetid: FAE099E4-6BE9-4637-934F-9F86FFDCAA6A
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UcxControllerNeedsReset, UcxControllerNeedsReset method [Buses], buses._ucxcontrollerneedsreset, ucxcontroller/UcxControllerNeedsReset
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	UcxControllerNeedsReset
product:
- Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# UcxControllerNeedsReset function


## -description


Initiates a non-Plug and Play (PnP) controller reset operation by queuing an event 
        into the controller reset state machine.



## -parameters




### -param Controller [in]

A handle to the controller object to reset. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>.


## -returns



If the operation is successful, the method returns TRUE. Otherwise it returns FALSE.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>
 

 

