---
UID: NS:pointofservicedriverinterface._PosStatusUpdatedEventData
title: _PosStatusUpdatedEventData (pointofservicedriverinterface.h)
description: This structure contains data passed to the StatusUpdated event.
old-location: pos\posstatusupdatedeventdata.htm
tech.root: pos
ms.assetid: 382e5441-dce1-428b-90af-d57b5f930abb
ms.date: 02/23/2018
ms.keywords: PosStatusUpdatedEventData, PosStatusUpdatedEventData structure, _PosStatusUpdatedEventData, pointofservicedriverinterface/PosStatusUpdatedEventData, pos.posstatusupdatedeventdata
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
- PointOfServiceDriverInterface.h
api_name:
- PosStatusUpdatedEventData
product:
- Windows
targetos: Windows
req.typenames: PosStatusUpdatedEventData
---

# _PosStatusUpdatedEventData structure


## -description


This structure contains data passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn790040">StatusUpdated</a> event.


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn772232">PosEventDataHeader</a> structure that contains information about the event that was raised and the amount of memory, in bytes, that this event data uses.


### -field Status

Indicates a device-specific enumeration value.


### -field ExtendedStatus

Indicates a driver-specific value intended to be used by the vendor for diagnostic purposes.

