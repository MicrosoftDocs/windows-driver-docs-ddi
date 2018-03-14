---
UID: NF:ucxcontroller.UcxControllerNotifyTransportCharacteristicsChange
title: UcxControllerNotifyTransportCharacteristicsChange function
author: windows-driver-content
description: Notifies UCX about a new port change event from host controller.
old-location: buses\ucxcontrollernotifytransportcharacteristicschange.htm
old-project: usbref
ms.assetid: DB49DF98-8A5B-4528-B312-63CE3DFABEF2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcxControllerNotifyTransportCharacteristicsChange, UcxControllerNotifyTransportCharacteristicsChange function [Buses], buses.ucxcontrollernotifytransportcharacteristicschange, ucxcontroller/UcxControllerNotifyTransportCharacteristicsChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Ucxstubs.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ucxstubs.lib
-	Ucxstubs.dll
api_name:
-	UcxControllerNotifyTransportCharacteristicsChange
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# UcxControllerNotifyTransportCharacteristicsChange function


## -description


Notifies UCX about a new port change event from host controller.



## -syntax


````
void UcxControllerNotifyTransportCharacteristicsChange(
  _In_  UCXCONTROLLER                             UcxController,
  _Out_ PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS UcxControllerTransportCharacteristics
);
````


## -parameters




### -param Controller

TBD


### -param UcxControllerTransportCharacteristics [out]

A pointer to a <a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_transport_characteristics.md">UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS</a> structure that contains the updated transport characteristics.


#### - UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


## -returns



This function does not return a value.




## -see-also

<a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_get_transport_characteristics.md">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a>



 

 


