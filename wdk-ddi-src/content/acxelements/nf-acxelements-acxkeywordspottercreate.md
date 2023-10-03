---
UID: NF:acxelements.AcxKeywordSpotterCreate
tech.root: audio
title: AcxKeywordSpotterCreate
ms.date: 12/15/2022
targetos: Windows
description: The AcxKeywordSpotterCreate function is used to create an ACX keyword spotter object that that will be associated with a circuit device object parent.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
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
 - acxelements.h
api_name:
 - AcxKeywordSpotterCreate
f1_keywords:
 - AcxKeywordSpotterCreate
 - acxelements/AcxKeywordSpotterCreate
dev_langs:
 - c++
---

## -description

The **AcxKeywordSpotterCreate** function is used to create an ACX keyword spotter object that that will be associated with a circuit device object parent.

## -parameters

### -param Object

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the circuit.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the KeywordSpotter object with the parent WDF device object.

### -param Config

An initialized [ACX_KEYWORDSPOTTER_CONFIG structure](ns-acxelements-acx_keywordspotter_config.md) that describes the configuration of the keyword spotter.

### -param KeywordSpotter

A pointer to a location that receives the handle to the newly created ACXKEYWORDSPOTTER object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_KEYWORDSPOTTER_CALLBACKS_INIT(&keywordSpotterCallbacks);
    keywordSpotterCallbacks.EvtAcxKeywordSpotterRetrieveArm = CodecC_EvtAcxKeywordSpotterRetrieveArm;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignArm = CodecC_EvtAcxKeywordSpotterAssignArm;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignPatterns = CodecC_EvtAcxKeywordSpotterAssignPatterns;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignReset = CodecC_EvtAcxKeywordSpotterAssignReset;

    ACX_KEYWORDSPOTTER_CONFIG_INIT(&keywordSpotterCfg);
    keywordSpotterCfg.Pattern = &CONTOSO_KEYWORDCONFIGURATION_IDENTIFIER2;
    keywordSpotterCfg.Callbacks = &keywordSpotterCallbacks;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_KEYWORDSPOTTER_CONTEXT);
    attributes.ParentObject = Circuit;

    status = AcxKeywordSpotterCreate(Circuit, &attributes, &keywordSpotterCfg, Element);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
