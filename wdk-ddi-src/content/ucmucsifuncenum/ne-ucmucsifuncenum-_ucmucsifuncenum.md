---
UID: NE:ucmucsifuncenum._UCMUCSIFUNCENUM
title: _UCMUCSIFUNCENUM (ucmucsifuncenum.h)
tech.root: usbref
description: Defines values for all export functions called by a client driver of a UcmUcsiCx class extension. 
ms.assetid: 52d0d6bb-f1e5-4033-a329-49f424623f72
ms.date: 10/19/2018
keywords: ["_UCMUCSIFUNCENUM enumeration"]
f1_keywords:
 - "ucmucsifuncenum/_UCMUCSIFUNCENUM"
 - "_UCMUCSIFUNCENUM"
ms.keywords: _UCMUCSIFUNCENUM, UCMUCSIFUNCENUM, 
req.header: ucmucsifuncenum.h
req.include-header: UcmUcsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.ddi-compliance:
req.max-support:
req.typenames: UCMUCSIFUNCENUM
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ucmucsifuncenum.h
api_name: 
- _UCMUCSIFUNCENUM
targetos: Windows
ms.custom: RS5
---

# _UCMUCSIFUNCENUM enumeration

## -description
Defines values for all export functions called by a client driver of a UcmUcsiCx class extension. 


## -enum-fields

### -field UcmUcsiDeviceInitInitializeTableIndex 
UcmUcsiDeviceInitInitialize - initializes the **WDFDEVICE_INIT** provided by the framework.

### -field UcmUcsiDeviceInitializeTableIndex
UcmUcsiDeviceInitialize - initializes the UcmUcsiCx class extension.

### -field UcmUcsiConnectorCollectionCreateTableIndex 
UcmUcsiConnectorCollectionCreate - creates a connector collection object with UcmUcsiCx.

### -field UcmUcsiConnectorCollectionAddConnectorTableIndex 
UcmUcsiConnectorCollectionAddConnector - adds a connector to the connector collection object.

### -field UcmUcsiPpmCreateTableIndex 
UcmUcsiPpmCreate - creates a Platform Policy Manager (PPM) object.

### -field UcmUcsiPpmSetUcsiCommandRequestQueueTableIndex 
UcmUcsiPpmSetUcsiCommandRequestQueue - provides a framework queue object that is used to dispatch UCSI commands to the client driver.

### -field UcmUcsiPpmStartTableIndex 
UcmUcsiPpmStart - instructs the class extension to start sending requests to the client driver.

### -field UcmUcsiPpmStopTableIndex 
UcmUcsiPpmStop - instructs the class extension to stop sending requests to the client driver.

### -field UcmUcsiPpmNotificationTableIndex 
UcmUcsiPpmNotification - informs the UcmUcsiCx class extension about a UCSI notification.

### -field UcmucsiFunctionTableNumEntries 
End of this enumeration.

## -remarks

## -see-also

[Ucmucsicx.h](../ucmucsicx/index.md)
