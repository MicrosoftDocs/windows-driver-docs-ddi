---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_CREATE_STREAM
tech.root: audio
title: EVT_ACX_CIRCUIT_CREATE_STREAM
ms.date: 08/23/2021
targetos: Windows
description: The driver defines/specifies this callback to create circuit stream instances. 
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

The driver defines/specifies this callback to create circuit stream instances. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [WDF - Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) associated with the specified ACXCIRCUIT. 

### -param Circuit

The ACXCIRCUIT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)) associated with the new stream instance.

### -param Pin

The ACXPIN object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects) associated with the new stream instance.  

### -param StreamInit

The ACXSTREAM_INIT object. This is an opaque structure, that is used to define the stream initialization.

### -param StreamFormat

An ACXDATAFORMAT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects) that defines the stream data format. 

### -param SignalProcessingMode

A GUID identifying the audio signal processing mode of the new stream circuit. For more information about audio modes, see [Audio Signal Processing Modes](/windows-hardware/drivers/audio/audio-signal-processing-modes).

### -param VarArguments

An optional ACXOBJECTBAG object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects) containing additional arguments to be used to initialize the stream.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The first step in Stream Creation is creating the ACXSTREAM instance for each ACXCIRCUIT in the Endpoint Audio Path. ACX will call each circuit’s EvtAcxCircuitCreateStream. ACX will start with the head circuit and call each circuit’s CreateStream in order, ending with the tail circuit.
The drivers have an opportunity to do any initialization before or after the next circuit in the chain is invoked, see ACXSTREAMBRIDGE object for more information.

The Stream Creation Request is sent to the appropriate ACXPIN exposed as part of the head circuit’s topology generation by calling the EvtAcxCircuitCreateStream specified during head circuit creation.  

The driver receiving the stream creation callback performs the following operations:   

- It initializes the ACXSTREAM_INIT opaque stracture by using ACX defined DDIs (AcxStreamInit*)
- It creates the ACXSTREAM object using the AcxStreamCreate or AcxRtStreamCreate ACX DDI. The AcxRtStreamCreate is only used for streaming ACXPIN connected to upper user mode audio pipeline, all other circuits of the endpoint path must use the AcxStreamCreate DDI instead. 
- It creates any stream-specific elements (e.g. ACXAUDIOENGINE)
- It adds the elements to the ACXSTREAM object  
- It returns STATUS_SUCCESS to indicate that the stream creation callback completed successfully.

The stream communication channel between circuits in an audio path uses ACXTARGETSTREAM objects.
  
Once the default target circuit creates the ACXSTREAM object, each circuit will be given an opportunity to perform circuit-specific handling for the stream. Each circuit in turn performs one or more of the following actions:  

- Create and add a Context object to the ACXSTREAM with stream driver specific configuration or data  
- Return control to the ACX framework, which will perform the same action with the next circuit in the Endpoint Audio Path  


### Example

TBD - Thinking we should refer to the main ACX driver sample, as the code for this call back, I believe is 100s of lines.

Yes, please check the up-to-date sample. the code below is more a unit-test and not a real code, for example the elements added below, they didn't do anything. please take a look at the single stack example (which adds an audio engine). 

Example usage is shown below.

```cpp
    status = AcxCircuitInitAssignAcxCreateStreamCallback(
                                            circuitInit, 
                                            CodecR_EvtCircuitCreateStream);

NTSTATUS
CodecR_EvtCircuitCreateStream(
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

    This routine create a stream for the specified circuit.

Return Value:

    NT status value

--*/
{
    NTSTATUS                        status;
    PCODEC_RENDER_DEVICE_CONTEXT    devCtx;
    WDF_OBJECT_ATTRIBUTES           attributes;
    ACXSTREAM                       stream;
    CODEC_STREAM_CONTEXT *          streamCtx;
    ACXELEMENT                      elements[2] = {0};
    ACX_ELEMENT_CONFIG              elementCfg;
    CODEC_ELEMENT_CONTEXT *         elementCtx;
    ACX_STREAM_CALLBACKS            streamCallbacks;
    ACX_RT_STREAM_CALLBACKS         rtCallbacks;
    CRenderStreamEngine *           renderStreamEngine = NULL;
    CCaptureStreamEngine *          captureStreamEngine = NULL;
    CODEC_PIN_TYPE                  codecPinType;
    PCODEC_PIN_CONTEXT              pinCtx;
    ACX_PIN_TYPE                    pinType;
    CODEC_RENDER_CIRCUIT_CONTEXT *  circuitCtx;

    PAGED_CODE();
    UNREFERENCED_PARAMETER(SignalProcessingMode);
    UNREFERENCED_PARAMETER(VarArguments);

    ASSERT(IsEqualGUID(*SignalProcessingMode, AUDIO_SIGNALPROCESSINGMODE_RAW));

    ASSERT(Circuit != NULL);
    circuitCtx = GetRenderCircuitContext(Circuit);
    ASSERT(circuitCtx);

    devCtx = GetRenderDeviceContext(Device);
    ASSERT(devCtx != NULL);
    UNREFERENCED_PARAMETER(devCtx);

    pinCtx = GetCodecPinContext(Pin);
    codecPinType = pinCtx->CodecPinType;

    pinType = AcxPinGetType(Pin);


```

## -see-also

[acxcircuit.h header](index.md)

READY2GO (with some comments above about the sample).