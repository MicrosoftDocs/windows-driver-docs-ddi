---
UID: NS:ksmedia._KSAUDIOMODULE_NOTIFICATION
title: _KSAUDIOMODULE_NOTIFICATION
author: windows-driver-content
description: The KSAUDIOMODULE_NOTIFICATION structure describes the properties associated with audio modules change notification.
old-location: audio\ksaudiomodule_notification.htm
old-project: audio
ms.assetid: 92A9462C-0E8C-4012-9374-3437BB220502
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _KSAUDIOMODULE_NOTIFICATION, *PKSAUDIOMODULE_NOTIFICATION, KSAUDIOMODULE_NOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIOMODULE_NOTIFICATION
req.alt-loc: Ksmedia.h
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
req.typenames: *PKSAUDIOMODULE_NOTIFICATION, KSAUDIOMODULE_NOTIFICATION
---

# _KSAUDIOMODULE_NOTIFICATION structure



## -description
The <b>KSAUDIOMODULE_NOTIFICATION</b> structure describes the  properties associated with audio  modules change notification.



## -syntax

````
typedef struct _KSAUDIOMODULE_NOTIFICATION {
  union {
    struct {
      GUID  DeviceId;
      GUID  ClassId;
      ULONG InstanceId;
      ULONG Reserved;
    } ProviderId;
    LONGLONG  Alignment;
  };
} KSAUDIOMODULE_NOTIFICATION, *PKSAUDIOMODULE_NOTIFICATION;
````


## -struct-fields

### -field ProviderId

A structure that specifies the ProviderId of the audio module notification.


### -field DeviceId

Specifies the DeviceId of the audio module notification. The DeviceId matches the value returned in <a href="https://msdn.microsoft.com/CD9C5FCD-FB2A-4B21-A15E-BA520C3311A7">KSPROPERTY_AUDIOMODULE_NOTIFICATION_DEVICE_ID</a>.


### -field ClassId

The ClassId of the audio module. The ClassId is an identifier that establishes what type of module this is. The value and mapping is established by the ISV and IHV. 


### -field InstanceId

The InstanceId of the audio module.  The InstanceId is a unique identifier that distinguishes this instance of a module from another instance of an module. 


### -field Reserved

This member is reserved.

</dd>
</dl>

### -field Alignment

Specifies the value that is used for alignment. 


## -remarks
The Audio module notification KSNOTIFICATIONID_AudioModule is defined in Ksmedia.h as shown here. 



For more information about audio modules, see  <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. </p>