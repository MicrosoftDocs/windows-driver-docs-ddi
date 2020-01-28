---
UID: NS:ucxcontroller._UCX_CONTROLLER_RESET_COMPLETE_INFO
title: _UCX_CONTROLLER_RESET_COMPLETE_INFO (ucxcontroller.h)
description: Contains information about the operation to reset the controller. This is used by the client driver in its EVT_UCX_CONTROLLER_RESET callback function.
old-location: buses\_ucx_controller_reset_complete_info.htm
tech.root: usbref
ms.assetid: 72935645-0567-4FC9-962C-3E823C08D001
ms.date: 05/07/2018
ms.keywords: "*PUCX_CONTROLLER_RESET_COMPLETE_INFO, P_UCX_CONTROLLER_RESET_COMPLETE_INFO, P_UCX_CONTROLLER_RESET_COMPLETE_INFO structure pointer [Buses], UCX_CONTROLLER_RESET_COMPLETE_INFO, UCX_CONTROLLER_RESET_COMPLETE_INFO structure [Buses], _UCX_CONTROLLER_RESET_COMPLETE_INFO, buses._ucx_controller_reset_complete_info, ucxcontroller/P_UCX_CONTROLLER_RESET_COMPLETE_INFO, ucxcontroller/_UCX_CONTROLLER_RESET_COMPLETE_INFO"
f1_keywords:
 - "ucxcontroller/UCX_CONTROLLER_RESET_COMPLETE_INFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ucxcontroller.h
api_name:
- UCX_CONTROLLER_RESET_COMPLETE_INFO
product:
- Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_RESET_COMPLETE_INFO, *PUCX_CONTROLLER_RESET_COMPLETE_INFO
---

# _UCX_CONTROLLER_RESET_COMPLETE_INFO structure


## -description


Contains information about the operation to reset the controller. This is used by the client driver in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_reset">EVT_UCX_CONTROLLER_RESET</a> callback function.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field UcxControllerState

The UCX controller state after reset. 


### -field UcxCoordinated

Indicates if the reset was coordinated with UCX (TRUE) or not (FALSE).


## -remarks



This structure is populated by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/nf-ucxcontroller-ucxcontrollerresetcomplete">UcxControllerResetComplete</a>.



