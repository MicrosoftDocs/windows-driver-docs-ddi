---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
title: EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION (ucxcontroller.h)
description: UCX invokes this callback function to specify its preference in transport characteristics for which the client driver must send notifications when changes occur.
old-location: buses\evt_ucx_controller_set_transport_characteristics_change_notification.htm
tech.root: usbref
ms.assetid: 559D2215-B78C-41EA-9E2C-6E67AE5276BE
ms.date: 05/07/2018
keywords: ["EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION callback function"]
ms.keywords: "*PFN_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, *PFN_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION callback function pointer [Buses], EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION callback, EvUcxControllerSetTransportCharacteristicsChangeNotification, EvUcxControllerSetTransportCharacteristicsChangeNotification callback function [Buses], buses.evt_ucx_controller_set_transport_characteristics_change_notification, ucxcontroller/EvUcxControllerSetTransportCharacteristicsChangeNotification"
f1_keywords:
 - "ucxcontroller/*PFN_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION"
 - "*PFN_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION"
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
- PFN_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION callback function


## -description


UCX invokes this callback function to specify its preference in transport characteristics for which the client driver must send notifications when changes occur. 


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param ChangeNotificationFlags [in]

 A bitwise option of flags that indicate the type transport characteristics in which UCX is interested. The flags are defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/ns-ucxcontroller-_ucx_controller_transport_characteristics_change_flags">UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS</a>.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers its implementation with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

For efficient power consumption, UCX invokes this callback function to specify the transport characteristics in which UCX is interested. 

It is likely that if the client driver keeps looking for changes in transport characteristics in the controller. This may result in a high power consumption and may be inefficient if there are no USB device drivers registered for that change notification. To optimize the power consumption, UCX invokes this callback function to  let the client driver know if any clients are registered for changes. This callback function passes the change notification flags as parameter. If a flag is set, it indicates that there is at least one device driver registered. If the flag is not set, it means that there are no clients registered and hence the controller can optimize power. 

<div class="alert"><b>Note</b>  It is optional for controller drivers to register or make use of these callback functions. It is valid for a controller driver to invoke the change notification even if UCX has indicated that there are no clients registered for it.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a>
 

 

