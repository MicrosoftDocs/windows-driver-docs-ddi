---
UID: NS:ucxcontroller._UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS
title: _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS (ucxcontroller.h)
description: Stores the transport characteristics at relevant points in time. This structure is used in the EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function.
old-location: buses\ucx_controller_transport_characteristics.htm
tech.root: usbref
ms.assetid: 9F267427-8D70-45D5-A8E6-67A1C6B73CDB
ms.date: 05/07/2018
keywords: ["_UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS structure"]
ms.keywords: "*PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS structure pointer [Buses], UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS structure [Buses], _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, buses.ucx_controller_transport_characteristics, ucxcontroller/PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, ucxcontroller/UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS"
f1_keywords:
 - "ucxcontroller/UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS"
 - "UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS"
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
- UcxController.h
api_name:
- UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, *PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS
---

# _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS structure


## -description


Stores the transport characteristics at relevant points in time. This structure is used in the   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_get_transport_characteristics">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a> callback function.


## -struct-fields




### -field TransportCharacteristicsFlags

A bitmask that indicates to the client driver the transport characteristics that are available and are returned in this structure. 




If USB_TRANSPORT_CHARACTERISTICS_LATENCY_AVAILABLE 

is set, <b>CurrentRoundtripLatencyInMilliSeconds</b> contains valid information. Otherwise , it must not be used by the client driver. 




If USB_TRANSPORT_CHARACTERISTICS_BANDWIDTH_AVAILABLE 

is set, <b>MaxPotentialBandwidth</b> contains valid information. Otherwise, it must not be used by the client driver.  


### -field CurrentRoundtripLatencyInMilliSeconds

Contains the current round-trip delay in milliseconds from the time a non-isochronous transfer is received by the USB driver stack to the time that the transfer is completed.  

For MA-USB, the underlying network could be WiFi, WiGig, Ethernet etc. The delay can vary depending on the underlying network conditions. A client driver should query the latency periodically or whenever it is notified of a change. 



### -field MaxPotentialBandwidth

Contains the total bandwidth of the host controller’s shared transport. 

For MA-USB, the underlying network transport could be WiFi, WiGig, Ethernet etc. The total available bandwidth can vary depending on several factors such as the negotiation WiFi channel. A client driver should query the total bandwidth periodically or whenever it is notified of a change. 



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_get_transport_characteristics">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a>
 

 

