---
UID: NS:pointofservicedriverinterface._PosStatusUpdatedEventData
title: _PosStatusUpdatedEventData (pointofservicedriverinterface.h)
description: This structure contains data passed to the StatusUpdated event.
old-location: pos\posstatusupdatedeventdata.htm
tech.root: pos
ms.assetid: 382e5441-dce1-428b-90af-d57b5f930abb
ms.date: 02/23/2018
keywords: ["PosStatusUpdatedEventData structure"]
ms.keywords: PosStatusUpdatedEventData, PosStatusUpdatedEventData structure, _PosStatusUpdatedEventData, pointofservicedriverinterface/PosStatusUpdatedEventData, pos.posstatusupdatedeventdata
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
targetos: Windows
req.typenames: PosStatusUpdatedEventData
f1_keywords:
 - _PosStatusUpdatedEventData
 - pointofservicedriverinterface/_PosStatusUpdatedEventData
 - PosStatusUpdatedEventData
 - pointofservicedriverinterface/PosStatusUpdatedEventData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - PosStatusUpdatedEventData
---

# _PosStatusUpdatedEventData structure


## -description

This structure contains data passed to the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn790040(v=vs.85)">StatusUpdated</a> event.

## -struct-fields

### -field Header

A <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn772232(v=vs.85)">PosEventDataHeader</a> structure that contains information about the event that was raised and the amount of memory, in bytes, that this event data uses.

### -field Status

Indicates a device-specific enumeration value.

### -field ExtendedStatus

Indicates a driver-specific value intended to be used by the vendor for diagnostic purposes.

