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

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Pin

TBD - An existing (or new TBD?) ACXPIN object.  

### -param StreamInit

Defined by a ACXSTREAM_INIT opaque structure, that is used to define the stream initialization.

### -param StreamFormat

An ACXDATAFORMAT object that defines the stream data format.  Use the TBD function to initialize the ACXDATAFORMAT object before using it here. 

### -param SignalProcessingMode

The AUDIO_SIGNALPROCESSINGMODE to be used for new stream circuits. These are the signal processing modes that TBD. For more information about audio modes, see [Audio Signal Processing Modes](/windows-hardware/drivers/audio/audio-signal-processing-modes).

TBD single GUID - `_In_    const GUID    * SignalProcessingMode`

### -param VarArguments

Additional arguments that are provided to TBD. TBD - if these additional arguments are not currently required, for your stream creation, they do not need to implemented???? TBD 


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The first step in Stream Creation is creating the ACXSTREAM instance for each ACXCIRCUIT in the Endpoint Audio Path. ACX will call each circuit’s EvtAcxCircuitCreateStream. ACX will start with the head circuit and call each circuit’s CreateStream in order, ending with the tail circuit. The order can be reversed by specifying the AcxStreamBridgeInvertChangeStateSequence flag for the Stream Bridge. After all circuits have created a stream object, the stream objects will handle the following logic. Depending on requirements, a 3rd party Endpoint Manager may be given the opportunity to specify different ordering.  

The Stream Creation Request is sent to the appropriate PIN generated as part of the head circuit’s topology generation by calling the EvtAcxCircuitCreateStream specified during head circuit creation.  

The circuit is the circuit that initially handles the stream creation request.   

- It allocates the AcxStreamConfig structure and fills it in  
- It creates the ACXSTREAM object   
- It creates any stream-specific elements (e.g. ACXVOLUME)  
- It adds the elements to the ACXSTREAM object  
- It returns the ACXSTREAM object that was created to the ACX framework  

The communication channel between circuits in an audio path uses ACXTARGETSTREAM objects. I will assume for this design that each circuit will have access to an IO Queue for the circuit in front of it and the circuit behind it in the Endpoint Audio Path. It is assumed that an Endpoint Audio Path is linear and bi-directional. The actual IO Queue handling will be performed by the ACX framework. 
  
Once the default target circuit creates the ACXSTREAM object, each circuit will be given an opportunity to perform circuit-specific handling for the stream. Each circuit in turn performs one or more of the following actions:  

- Create and add a Context object to the ACXSTREAM with circuit-specific configuration or data  
- Return control to the ACX framework, which will perform the same action with the next circuit in the Endpoint Audio Path  


### Example

TBD - Thinking we should refer to the main ACX driver sample, as the code for this call back, I believe is 100s of lines.

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

