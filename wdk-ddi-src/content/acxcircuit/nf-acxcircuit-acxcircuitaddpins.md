---
UID: NF:acxcircuit.AcxCircuitAddPins
tech.root: audio
title: AcxCircuitAddPins
ms.date: 08/16/2021
targetos: Windows
description: The AcxCircuitAddPins function adds pins to an existing (TBD or new?) Acx circuit. 
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
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - AcxCircuitAddPins
f1_keywords:
 - AcxCircuitAddPins
 - acxcircuit/AcxCircuitAddPins
dev_langs:
 - c++
---

## -description

The AcxCircuitAddPins function adds pins to an existing (TBD or new?) Acx circuit. 

## -parameters

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).
 
### -param Pins

TBD - An existing (or new TBD?) ACXPIN object.  (DocsTeam - need link to ACX Object Summary topic).

### -param PinsCount

TBD - The number of pins that will be added to the circuit. This is a TBD zero / one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxCircuit has an input pin and an output pin (ACXPIN), and it aggregates one or more AcxElements. 

TBD - The default pin ID has a value of TBD and is used to TBD...

Each ACXCIRCUIT has at least one Sink Pin and one Source Pin. These Pins are used by the ACX framework to expose the circuit’s connections to the audio stack. For a Render circuit, the Source Pin is used to control the render behavior of any stream created from the circuit. For a Capture circuit, the Sink Pin is used to control the capture behavior of any stream created from the circuit.  

ACXPIN is the object used to control streaming in the Audio Path. The head ACXCIRCUIT is responsible for creating the appropriate ACXPIN object(s) for the Endpoint Audio Path at circuit creation time and registering the ACXPINs with ACX. The ACXCIRCUIT only needs to create the render or capture pin or pins for the Circuit; the ACX framework will create the other pin needed to connect to and communicate with the circuit.  

### Example

Example usage is shown below.

```cpp
    ACXPIN pin;  
 
    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
    attributes.ParentObject = circuit;

    status = AcxPinCreate(circuit, &attributes, &pinCfg, &(pin[1]));
  
    // Add the supported formats to the Default mode for the circuit
    //
    formatList = AcxPinGetRawDataFormatList(pin[1]);
  
    status = AcxDataFormatListAddDataFormat(formatList, formatPcm16000c1);
  
    //
    // Add the default streaming pin, using default pin id. 
    //
    status = AcxCircuitAddPins(circuit, &(pin[1]), 1);
```

## -see-also

[acxcircuit.h header](index.md)

