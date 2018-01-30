---
UID: NS:ucxcontroller._UCX_CONTROLLER_RESET_COMPLETE_INFO
title: "_UCX_CONTROLLER_RESET_COMPLETE_INFO"
author: windows-driver-content
description: Contains information about the operation to reset the controller. This is used by the client driver in its EVT_UCX_CONTROLLER_RESET callback function.
old-location: buses\_ucx_controller_reset_complete_info.htm
old-project: usbref
ms.assetid: 72935645-0567-4FC9-962C-3E823C08D001
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PUCX_CONTROLLER_RESET_COMPLETE_INFO, _UCX_CONTROLLER_RESET_COMPLETE_INFO, UCX_CONTROLLER_RESET_COMPLETE_INFO structure [Buses], ucxcontroller/P_UCX_CONTROLLER_RESET_COMPLETE_INFO, P_UCX_CONTROLLER_RESET_COMPLETE_INFO, UCX_CONTROLLER_RESET_COMPLETE_INFO, ucxcontroller/_UCX_CONTROLLER_RESET_COMPLETE_INFO, buses._ucx_controller_reset_complete_info, P_UCX_CONTROLLER_RESET_COMPLETE_INFO structure pointer [Buses]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucxcontroller.h
apiname:
-	UCX_CONTROLLER_RESET_COMPLETE_INFO
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_RESET_COMPLETE_INFO, *PUCX_CONTROLLER_RESET_COMPLETE_INFO
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_RESET_COMPLETE_INFO structure


## -description


Contains information about the operation to reset the controller. This is used by the client driver in its <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_reset.md">EVT_UCX_CONTROLLER_RESET</a> callback function.


## -syntax


````
typedef struct _UCX_CONTROLLER_RESET_COMPLETE_INFO {
  ULONG                Size;
  UCX_CONTROLLER_STATE UcxControllerState;
  BOOLEAN              UcxCoordinated;
} UCX_CONTROLLER_RESET_COMPLETE_INFO, *P_UCX_CONTROLLER_RESET_COMPLETE_INFO;
````


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field UcxControllerState

The UCX controller state after reset. 


### -field UcxCoordinated

Indicates if the reset was coordinated with UCX (TRUE) or not (FALSE).


## -remarks


This structure is populated by a call to <a href="..\ucxcontroller\nf-ucxcontroller-ucxcontrollerresetcomplete.md">UcxControllerResetComplete</a>.


