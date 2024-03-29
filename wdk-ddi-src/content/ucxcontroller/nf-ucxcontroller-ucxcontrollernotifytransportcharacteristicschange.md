---
UID: NF:ucxcontroller.UcxControllerNotifyTransportCharacteristicsChange
title: UcxControllerNotifyTransportCharacteristicsChange function (ucxcontroller.h)
description: Notifies UCX about a new port change event from host controller.
old-location: buses\ucxcontrollernotifytransportcharacteristicschange.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UcxControllerNotifyTransportCharacteristicsChange function"]
ms.keywords: UcxControllerNotifyTransportCharacteristicsChange, UcxControllerNotifyTransportCharacteristicsChange function [Buses], buses.ucxcontrollernotifytransportcharacteristicschange, ucxcontroller/UcxControllerNotifyTransportCharacteristicsChange
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxControllerNotifyTransportCharacteristicsChange
 - ucxcontroller/UcxControllerNotifyTransportCharacteristicsChange
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ucxstubs.lib
 - Ucxstubs.dll
api_name:
 - UcxControllerNotifyTransportCharacteristicsChange
---

# UcxControllerNotifyTransportCharacteristicsChange function


## -description

Notifies UCX about a new port change event from host controller.

## -parameters

### -param Controller

<p> A handle to the UCX controller that the client driver received in a previous call to  the <a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)"><b>UcxControllerCreate</b></a> method.</p>

### -param UcxControllerTransportCharacteristics [out]


A pointer to a <a href="/windows-hardware/drivers/ddi/ucxcontroller/ns-ucxcontroller-_ucx_controller_transport_characteristics">UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS</a> structure that contains the updated transport characteristics.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_get_transport_characteristics">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a>
