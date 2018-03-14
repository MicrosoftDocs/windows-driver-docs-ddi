---
UID: NS:portcls._PCNOTIFICATION_BUFFER
title: "_PCNOTIFICATION_BUFFER"
author: windows-driver-content
description: The notification buffer used by IPortClsNotifications.
old-location: audio\pcnotification_buffer.htm
old-project: audio
ms.assetid: EEE091E4-29D1-4C6F-B543-C54736660CCA
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PPCNOTIFICATION_BUFFER, PCNOTIFICATION_BUFFER, PCNOTIFICATION_BUFFER structure [Audio Devices], PPCNOTIFICATION_BUFFER, PPCNOTIFICATION_BUFFER structure pointer [Audio Devices], _PCNOTIFICATION_BUFFER, audio.pcnotification_buffer, portcls/PCNOTIFICATION_BUFFER, portcls/PPCNOTIFICATION_BUFFER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Portcls.h
api_name:
-	PCNOTIFICATION_BUFFER
product: Windows
targetos: Windows
req.typenames: PCNOTIFICATION_BUFFER, *PPCNOTIFICATION_BUFFER
---

# _PCNOTIFICATION_BUFFER structure


## -description


The notification buffer used by <a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>.


## -syntax


````
typedef struct _PCNOTIFICATION_BUFFER {
  UCHAR NotificationBuffer[1];
} PCNOTIFICATION_BUFFER, *PPCNOTIFICATION_BUFFER;
````


## -struct-fields




### -field NotificationBuffer

The notification buffer used by <a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>.


## -see-also

<a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>



 

 


