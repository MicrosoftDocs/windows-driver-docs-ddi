---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS
title: EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS (ucxcontroller.h)
description: UCX invokes this callback to retrieve the host controller characteristics.
old-location: buses\evt_ucx_controller_get_transport_characteristics.htm
tech.root: usbref
ms.assetid: 4394199C-6644-4E11-BDAF-625C2F94DEE8
ms.date: 05/07/2018
keywords: ["EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function"]
ms.keywords: "*PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS, *PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function pointer [Buses], EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS, EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback, EvUcxControllerGetTransportCharacteristics, EvUcxControllerGetTransportCharacteristics callback function [Buses], buses.evt_ucx_controller_get_transport_characteristics, ucxcontroller/EvUcxControllerGetTransportCharacteristics"
f1_keywords:
 - "ucxcontroller/*PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS"
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- UcxController.h
api_name:
- PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function


## -description


 UCX invokes this callback to retrieve the host controller characteristics.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param UcxControllerTransportCharacteristics [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/ns-ucxcontroller-_ucx_controller_transport_characteristics">UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS</a> structure that the client driver for the host controller fills with transport characteristics.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers its implementation with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

This callback function is optional. Whenever transport characteristics change, the client driver is responsible for notifying UCX that one of the characteristics have changed using a new function <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/nf-ucxcontroller-ucxcontrollernotifytransportcharacteristicschange">UcxControllerNotifyTransportCharacteristicsChange</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a>
 

 

