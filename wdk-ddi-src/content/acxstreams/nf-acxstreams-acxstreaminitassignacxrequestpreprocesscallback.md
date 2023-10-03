---
UID: NF:acxstreams.AcxStreamInitAssignAcxRequestPreprocessCallback
tech.root: audio
title: AcxStreamInitAssignAcxRequestPreprocessCallback
ms.date: 12/16/2022
targetos: Windows
description: The AcxStreamInitAssignAcxRequestPreprocessCallback function assigns an  AcxRequestPreprocessCallback to a stream.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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

The **AcxStreamInitAssignAcxRequestPreprocessCallback** function assigns an AcxRequestPreprocessCallback to a stream.

## -parameters

### -param StreamInit

Defined by a ACXSTREAM_INIT object, that is used to define the stream initialization. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param EvtObjectAcxRequestPreprocess

An EvtObjectAcxRequestPreprocess that will be called by the ACX framework before any internal handling of the request is performed.

### -param DriverContext

An optional ACXCONTEXT object that represents the current driver context.

### -param RequestType

The [ACX_REQUEST_TYPE enum](..\acxrequest\ne-acxrequest-acx_request_type.md) that is that is used to define the request type. If AcxRequestTypeAny is specified, EvtObjectAcxRequestProcess will be called for all requests.

### -param Set

A pointer to a GUID that represents a KSPROPERTY SET, for example [KSPROPSETID_RtAudio](/windows-hardware/drivers/audio/kspropsetid-rtaudio). If NULL or GUID_NULL are specified, EvtObjectAcxRequestPreprocess will be called for each request that matches RequestType

### -param Id

A value that represents a KSPROPERTY Id. For example a A [KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT](/windows-hardware/drivers/audio/ksproperty-rtaudio-register-notification-event) that uses a [KSRTAUDIO_NOTIFICATION_EVENT_PROPERTY structure](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksrtaudio_notification_event_property). If AcxItemIdAny is specified, EvtObjectAcxRequestPreprocess will be called for each property for the specified Set.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

AcxStreamInitAssignAcxRequestPreprocessCallback gives the driver the opportunity to handle any requests before ACX performs framework handling. The driver can call [AcxStreamDispatchAcxRequest](nf-acxstreams-acxstreamdispatchacxrequest.md) to allow ACX to handle the request. If the driver handles the request itself, it can call WdfRequestComplete or WdfRequestCompleteWithInformation to complete the request.

The driver must call either AcxStreamDispatchAcxRequest or WdfRequestComplete (or WdfRequestCompleteWithInformation). The driver must not call more than one of these APIs with the request.

The driver can register more than one AcxRequestPreprocessCallback. The ACX framework will call the first assigned AcxRequestPreprocessCallback that matches a request.

### Example

Example usage is shown below.

```cpp
    //
    // Intercept register and unregister events properties.
    //
    status = AcxStreamInitAssignAcxRequestPreprocessCallback(
                                            StreamInit, 
                                            EvtStreamRequestPreprocessRegisterNotificationEvent,
                                            (ACXCONTEXT)Circuit,
                                            AcxRequestTypeProperty,
                                            &KSPROPSETID_RtAudio, 
                                            KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT);

    //
    // Intercept all other RtAudio properties - this must be after the above Assign call
    // since the above Assign call is more specific.
    //
    status = AcxStreamInitAssignAcxRequestPreprocessCallback(
                                            StreamInit, 
                                            EvtStreamRequestPreprocessRtAudio,
                                            (ACXCONTEXT)Circuit,
                                            AcxRequestTypeProperty,
                                            &KSPROPSETID_RtAudio, 
                                            AcxItemIdAny);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
