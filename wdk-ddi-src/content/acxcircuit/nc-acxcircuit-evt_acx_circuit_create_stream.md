---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_CREATE_STREAM
tech.root: audio
title: EVT_ACX_CIRCUIT_CREATE_STREAM
ms.date: 11/02/2021
targetos: Windows
description: The driver defines the EVT_ACX_CIRCUIT_CREATE_STREAM callback to create circuit stream instances.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - LibDef
api_location:
 - acxcircuit.h
api_name:
 - EVT_ACX_CIRCUIT_CREATE_STREAM
f1_keywords:
 - EVT_ACX_CIRCUIT_CREATE_STREAM
 - acxcircuit/EVT_ACX_CIRCUIT_CREATE_STREAM
dev_langs:
 - c++
---

## -description

The driver defines the **EVT_ACX_CIRCUIT_CREATE_STREAM** callback to create circuit stream instances.

## -parameters

### -param Device

A WDFDEVICE object (described in  [WDF - Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) associated with the specified ACXCIRCUIT.

### -param Circuit

The ACXCIRCUIT object  associated with the new stream instance. For more information about ACX Objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Pin

The ACXPIN ACX object associated with the new stream instance.  

### -param StreamInit

The ACXSTREAM_INIT ACX object. This is an opaque structure, that is used to define the stream initialization.

### -param StreamFormat

An ACXDATAFORMAT ACX object that defines the stream data format.

### -param SignalProcessingMode

A GUID identifying the audio signal processing mode of the new stream circuit. For more information about audio modes, see [Audio Signal Processing Modes](/windows-hardware/drivers/audio/audio-signal-processing-modes).

### -param VarArguments

An optional ACXOBJECTBAG object containing additional arguments to be used to initialize the stream.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The first step in Stream Creation is creating the ACXSTREAM instance for each ACXCIRCUIT in the Endpoint Audio Path. ACX will call each circuit’s EvtAcxCircuitCreateStream. ACX will start with the head circuit and call each circuit’s CreateStream in order, ending with the tail circuit.

The drivers have an opportunity to do any initialization before or after the next circuit in the chain is invoked, refer to the  ACXSTREAMBRIDGE object for more information.

The Stream Creation Request is sent to the appropriate ACXPIN exposed as part of the head circuit’s topology generation by calling the EvtAcxCircuitCreateStream specified during head circuit creation.

The driver receiving the stream creation callback performs the following operations:

- It initializes the ACXSTREAM_INIT opaque structure by using ACX defined DDIs (AcxStreamInit*)
- It creates the ACXSTREAM object using the AcxStreamCreate or AcxRtStreamCreate ACX DDI. The AcxRtStreamCreate is only used for streaming ACXPIN connected to upper user mode audio pipeline, all other circuits of the endpoint path must use the AcxStreamCreate DDI instead. 
- It creates any stream-specific elements, for example ACXAUDIOENGINE.
- It adds the elements to the ACXSTREAM object.
- It returns STATUS_SUCCESS to indicate that the stream creation callback completed successfully.

The stream communication channel between circuits in an audio path uses ACXTARGETSTREAM objects.

Once the default target circuit creates the ACXSTREAM object, each circuit will be given an opportunity to perform circuit-specific handling for the stream. Each circuit in turn performs one or more of the following actions:

- Create and add a Context object to the ACXSTREAM with stream driver specific configuration or data.
- Return control to the ACX framework, which will perform the same action with the next circuit in the Endpoint Audio Path.

### Example

Example usage is shown below.

```cpp
    status = AcxCircuitInitAssignAcxCreateStreamCallback(
                                            circuitInit, 
                                            CodecC_EvtCircuitCreateStream);

NTSTATUS
CodecC_EvtCircuitCreateStream(
    _In_    WDFDEVICE       Device,
    _In_    ACXCIRCUIT      Circuit,
    _In_    ACXPIN          Pin,
    _In_    PACXSTREAM_INIT StreamInit,
    _In_    ACXDATAFORMAT   StreamFormat,
    _In_    const GUID    * SignalProcessingMode,
    _In_    ACXOBJECTBAG    VarArguments
    )
/*++

Routine Description:

    This routine creates a stream for the specified circuit.

Return Value:

    NT status value

--*/
{
    NTSTATUS                        status;
    PCODEC_CAPTURE_DEVICE_CONTEXT   devCtx;
    WDF_OBJECT_ATTRIBUTES           attributes;
    ACXSTREAM                       stream;
    CODEC_STREAM_CONTEXT *          streamCtx;
    ACXELEMENT                      elements[2] = {0};
    ACX_ELEMENT_CONFIG              elementCfg;
    CODEC_ELEMENT_CONTEXT *         elementCtx;
    ACX_STREAM_CALLBACKS            streamCallbacks;
    ACX_RT_STREAM_CALLBACKS         rtCallbacks;
    CCaptureStreamEngine *          streamEngine = NULL;
    CODEC_CAPTURE_CIRCUIT_CONTEXT * circuitCtx;
    CODEC_PIN_CONTEXT *             pinCtx;

    PAGED_CODE();
    UNREFERENCED_PARAMETER(SignalProcessingMode);
    UNREFERENCED_PARAMETER(VarArguments);

    ASSERT(IsEqualGUID(*SignalProcessingMode, AUDIO_SIGNALPROCESSINGMODE_RAW));

    devCtx = GetCaptureDeviceContext(Device);
    ASSERT(devCtx != NULL);

    circuitCtx = GetCaptureCircuitContext(Circuit);
    ASSERT(circuitCtx != NULL);

    pinCtx = GetCodecPinContext(Pin);
    ASSERT(pinCtx != NULL);

    //
    // Set circuit-callbacks.
    //
    status = AcxStreamInitAssignAcxRequestPreprocessCallback(
                                            StreamInit, 
                                            CodecC_EvtStreamRequestPreprocess,
                                            (ACXCONTEXT)AcxRequestTypeAny, // dbg only
                                            AcxRequestTypeAny,
                                            NULL, 
                                            AcxItemIdNone);
    if (!NT_SUCCESS(status)) 
    {
        ASSERT(FALSE);
        goto exit;
    }

    /*
    //
    // Add properties, events and methods.
    //
    status = AcxStreamInitAssignProperties(StreamInit,
                                         StreamProperties,
                                         StreamPropertiesCount);
    */

    //
    // Init streaming callbacks.
    //
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    streamCallbacks.EvtAcxStreamPrepareHardware     = Codec_EvtStreamPrepareHardware;
    streamCallbacks.EvtAcxStreamReleaseHardware     = Codec_EvtStreamReleaseHardware;
    streamCallbacks.EvtAcxStreamRun                 = Codec_EvtStreamRun;
    streamCallbacks.EvtAcxStreamPause               = Codec_EvtStreamPause;

    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);
    if (!NT_SUCCESS(status))
    {
        ASSERT(FALSE);
        goto exit;
    } 

    //
    // Init RT streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
    rtCallbacks.EvtAcxStreamGetHwLatency            = Codec_EvtStreamGetHwLatency;
    rtCallbacks.EvtAcxStreamAllocateRtPackets       = Codec_EvtStreamAllocateRtPackets;
    rtCallbacks.EvtAcxStreamFreeRtPackets           = Codec_EvtStreamFreeRtPackets;
    rtCallbacks.EvtAcxStreamGetCapturePacket        = CodecC_EvtStreamGetCapturePacket;
    rtCallbacks.EvtAcxStreamGetCurrentPacket        = Codec_EvtStreamGetCurrentPacket;
    rtCallbacks.EvtAcxStreamGetPresentationPosition = Codec_EvtStreamGetPresentationPosition;

    status = AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks);
    if (!NT_SUCCESS(status))
    {
        ASSERT(FALSE);
        goto exit;
    }
    
    //
    // Buffer notifications are supported.
    //
    AcxStreamInitSetAcxRtStreamSupportsNotifications(StreamInit);
    
    //
    // Create the stream.
    //
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_STREAM_CONTEXT);   

    attributes.EvtDestroyCallback = Codec_EvtStreamDestroy;

    status = AcxRtStreamCreate(Device, Circuit, &attributes, &StreamInit, &stream);
    if (!NT_SUCCESS(status)) 
    {
        ASSERT(FALSE);
        goto exit;
    }

    streamCtx = GetCodecStreamContext(stream);
    ASSERT(streamCtx);

    if (pinCtx->CodecPinType == CodecPinTypeKeyword)
    {
        PCODEC_KEYWORDSPOTTER_CONTEXT keywordSpotterCtx;

        keywordSpotterCtx = GetCodecKeywordSpotterContext(circuitCtx->KeywordSpotter);

        streamEngine = new(NonPagedPoolNx, DRIVER_TAG) CBufferedCaptureStreamEngine(stream, StreamFormat, (CKeywordDetector *) keywordSpotterCtx->KeywordDetector);
        if (streamEngine == NULL)
        {
            status = STATUS_INSUFFICIENT_RESOURCES;
            ASSERT(FALSE);
            goto exit;
        }
    }
    else
    {
        streamEngine = new(NonPagedPoolNx, DRIVER_TAG) CCaptureStreamEngine(stream, StreamFormat);
        if (streamEngine == NULL)
        {
            status = STATUS_INSUFFICIENT_RESOURCES;
            ASSERT(FALSE);
            goto exit;
        }
    }

    streamCtx->StreamEngine = (PVOID)streamEngine;
    streamEngine = NULL;

    //
    // Post stream creation initialization.
    // Create any custom stream-elements.
    // Add stream elements
```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO

EDITCOMPLETE