---
UID: NS:ucxcontroller._UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS
title: "_UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS"
author: windows-driver-content
description: Stores the transport characteristics at relevant points in time. This structure is used in the EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS callback function.
old-location: buses\ucx_controller_transport_characteristics.htm
old-project: usbref
ms.assetid: 9F267427-8D70-45D5-A8E6-67A1C6B73CDB
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS structure pointer [Buses], UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS structure [Buses], _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, buses.ucx_controller_transport_characteristics, ucxcontroller/PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, ucxcontroller/UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UcxController.h
api_name:
-	UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS, *PUCX_CONTROLLER_TRANSPORT_CHARACTERISTICS
---

# _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS structure


## -description


Stores the transport characteristics at relevant points in time. This structure is used in the   <a href="https://msdn.microsoft.com/4394199C-6644-4E11-BDAF-625C2F94DEE8">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a> callback function.


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




<a href="https://msdn.microsoft.com/4394199C-6644-4E11-BDAF-625C2F94DEE8">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a>
 

 

