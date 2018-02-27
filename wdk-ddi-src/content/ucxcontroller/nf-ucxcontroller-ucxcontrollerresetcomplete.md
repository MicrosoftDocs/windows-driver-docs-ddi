---
UID: NF:ucxcontroller.UcxControllerResetComplete
title: UcxControllerResetComplete function
author: windows-driver-content
description: Informs USB Host Controller Extension (UCX) that the reset operation has competed.
old-location: buses\_ucxcontrollerresetcomplete.htm
old-project: usbref
ms.assetid: 483147CF-B15D-435C-B5AA-31723D4C2A85
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcxControllerResetComplete, UcxControllerResetComplete method [Buses], buses._ucxcontrollerresetcomplete, ucxcontroller/UcxControllerResetComplete
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Ucxcontroller.h
apiname:
-	UcxControllerResetComplete
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# UcxControllerResetComplete function


## -description


Informs USB Host Controller Extension (UCX) that the reset operation has competed.


## -syntax


````
void UcxControllerResetComplete(
  [in] UCXCONTROLLER Controller
);
````


## -parameters




### -param Controller [in]

A handle to the controller object to reset. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>.


### -param UcxControllerResetCompleteInfo

TBD




## -returns



This method does not return a value.




## -see-also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxControllerResetComplete method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

