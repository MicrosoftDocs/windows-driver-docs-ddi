---
UID: NE:ucmucsifuncenum._UCMUCSIFUNCENUM
title: _UCMUCSIFUNCENUM
author: windows-driver-content
description: Defines values for all export functions called by a client driver of a UcmUcsiCx class extension. 
ms.assetid: 52d0d6bb-f1e5-4033-a329-49f424623f72
ms.author: windowsdriverdev
ms.date: 
ms.topic: enum
ms.keywords: _UCMUCSIFUNCENUM, UCMUCSIFUNCENUM, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ucmucsifuncenum.h
req.include-header: UcmucsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.ddi-compliance:
req.max-support:
req.typenames: UCMUCSIFUNCENUM
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ucmucsifuncenum.h
api_name: 
-	_UCMUCSIFUNCENUM
product: Windows
targetos: Windows
---

# _UCMUCSIFUNCENUM enumeration

## -description
Defines values for all export functions called by a client driver of a UcmUcsiCx class extension. 


## -enum-fields

### -field UcmUcsiDeviceInitInitializeTableIndex 
UcmUcsiDeviceInitInitialize function used to initialize the **WDFDEVICE_INIT** provided by the framework.

### -field UcmUcsiDeviceInitializeTableIndex
UcmUcsiDeviceInitialize function used to initialize the UcmUcsiCx class extension.

### -field UcmUcsiConnectorCollectionCreateTableIndex 


### -field UcmUcsiConnectorCollectionAddConnectorTableIndex 
### -field UcmUcsiPpmCreateTableIndex 
### -field UcmUcsiPpmSetUcsiCommandRequestQueueTableIndex 
### -field UcmUcsiPpmStartTableIndex 
### -field UcmUcsiPpmStopTableIndex 
### -field UcmUcsiPpmNotificationTableIndex 
### -field UcmucsiFunctionTableNumEntries 

## -remarks

## -see-also

[Ucmucsicx.h](..\ucmucsicx\index.md)