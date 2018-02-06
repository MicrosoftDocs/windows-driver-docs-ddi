---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_RESET
title: EVT_UCX_CONTROLLER_RESET
author: windows-driver-content
description: The client driver's implementation that UCX calls to reset the controller.
old-location: buses\evt_ucx_controller_reset.htm
old-project: usbref
ms.assetid: 8c01d677-5ce4-44f6-8342-2152e851de87
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ucx_controller_reset, EvtUcxControllerReset callback function [Buses], EvtUcxControllerReset, EVT_UCX_CONTROLLER_RESET, EVT_UCX_CONTROLLER_RESET, ucxcontroller/EvtUcxControllerReset, PEVT_UCX_CONTROLLER_RESET callback function pointer [Buses], PEVT_UCX_CONTROLLER_RESET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ucxcontroller.h
apiname:
-	PEVT_UCX_CONTROLLER_RESET
product: Windows
targetos: Windows
req.typenames: "*PUCM_PD_REQUEST_DATA_OBJECT, UCM_PD_REQUEST_DATA_OBJECT"
req.product: Windows 10 or later.
---

# EVT_UCX_CONTROLLER_RESET callback


## -description


The client driver's implementation that UCX calls to reset the controller.


## -prototype


````
EVT_UCX_CONTROLLER_RESET EvtUcxControllerReset;

VOID EvtUcxControllerReset(
  _In_ UCXCONTROLLER UcxController
)
{ ... }

typedef EVT_UCX_CONTROLLER_RESET PEVT_UCX_CONTROLLER_RESET;
````


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


## -returns


This callback function does not return a value.



## -remarks


The UCX client driver registers its <i>EVT_UCX_CONTROLLER_RESET</i> implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

The client driver indicates completion of this event by calling the <a href="..\ucxcontroller\nf-ucxcontroller-ucxcontrollerresetcomplete.md">UcxControllerResetComplete</a> method. Doing so ensures that UCX does not call <i>EVT_UCX_CONTROLLER_RESET</i> a second time before this event callback completes.

If the client driver calls <a href="..\ucxcontroller\nf-ucxcontroller-ucxcontrollerneedsreset.md">UcxControllerNeedsReset</a>, UCX calls this event callback function.  However, UCX may call this event callback function even when the client driver has not called <b>UcxControllerNeedsReset</b>. 



## -see-also

<a href="..\ucxcontroller\nf-ucxcontroller-ucxcontrollerresetcomplete.md">UcxControllerResetComplete</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>

<a href="..\ucxcontroller\nf-ucxcontroller-ucxcontrollerneedsreset.md">UcxControllerNeedsReset</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_CONTROLLER_RESET callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

