---
UID: NF:acxstreams.AcxStreamInitAssignAcxRequestPreprocessCallback
tech.root: audio
title: AcxStreamInitAssignAcxRequestPreprocessCallback
ms.date: 07/13/2021
targetos: Windows
description: The AcxStreamInitAssignAcxRequestPreprocessCallback function assigns an  AcxRequestPreprocessCallback to a stream. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef 
api_location:
 - acxstreams.h
api_name:
 - AcxStreamInitAssignAcxRequestPreprocessCallback
f1_keywords:
 - AcxStreamInitAssignAcxRequestPreprocessCallback
 - acxstreams/AcxStreamInitAssignAcxRequestPreprocessCallback
dev_langs:
 - c++
---

## -description

The AcxStreamInitAssignAcxRequestPreprocessCallback function assigns an  AcxRequestPreprocessCallback to a stream.

## -parameters

### -param StreamInit

Defined by a ACXSTREAM_INIT object, that is used to define the stream initialization. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param EvtObjectAcxRequestPreprocess

An optional EvtObjectAcxRequestPreprocess TBD TBD TBD.

### -param DriverContext

And ACXCONTEXT object that represents the current driver context.
 
### -param RequestType

The [ACX_REQUEST_TYPE enum](..\acxrequest\ne-acxrequest-acx_request_type.md) that is that is used to define the request type.

### -param Set

A pointer to a GUID that represents a KSPROPERTY SET, for example [KSPROPSETID_RtAudio](/windows-hardware/drivers/audio/kspropsetid-rtaudio).

### -param Id

The ID of the the process callback(TBD?). For example a A [KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT](/windows-hardware/drivers/audio/ksproperty-rtaudio-register-notification-event) that uses a [KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksrtaudio_notification_event_property).


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

TBD TBD TBD 

Is this function similar to IMiniportWaveRTStreamNotification::RegisterNotificationEvent?

TBD TBD TBD 

### Example

Example usage is shown below.

```cpp
   //
    // Intercept register and unregister events properties.
    //
    status = AcxStreamInitAssignAcxRequestPreprocessCallback(
                                            StreamInit, 
                                            C_EvtStreamRequestPreprocess,
                                            (ACXCONTEXT)Circuit,
                                            AcxRequestTypeProperty,
                                            &KSPROPSETID_RtAudio, 
                                            KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT);
```



## -see-also

[acxstreams.h header](index.md)

