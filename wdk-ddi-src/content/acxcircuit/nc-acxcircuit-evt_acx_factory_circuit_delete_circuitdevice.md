---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
ms.date: 12/14/2022
targetos: Windows
description: The EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE callback is invoked by ACX when the driver must delete a previously created WDFDEVICE associated with an ACXCIRCUIT object.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - LibDef
api_location:
 - acxcircuit.h
api_name:
 - EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE** callback is invoked by ACX when the driver must delete a previously created WDFDEVICE associated with an ACXCIRCUIT object.

## -parameters

### -param Parent

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is the parent of the WDFDEVICE referenced in Device object.

### -param Factory

The existing circuit factory ACXFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that must be deleted.  

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxFactoryCircuit represents a factory object capable of creating an ACXCIRCUIT on demand.

A driver can register one or more ACXFACTORYCIRCUIT with ACX, this action will let ACX know that the driver is capable of creating ACXCIRCUITs of a well defined type.

ACX invokes the ACXFACTORYCIRCUIT's callbacks when it detects that an audio path requires one of the factory provided ACXCIRCUITs.

This is an optional callback, if the EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE callback is not defined, ACX takes the default action of removing the specified WDFDEVICE from the list of enumerated devices. This action triggers a surprise-removed PnP notification to the child WDFDEVICE.

The ACXFACTORYCIRCUIT object supports dynamic ACXCIRCUITs, this means that each ACXCIRCUIT created by the factory is associated with a WDFDEVICE and these two objects have the same lifetime.

An AcxFactoryCircuit has a dedicated WDF queue. For more information about WDF queues, see [Framework Queue Objects](/windows-hardware/drivers/wdf/framework-queue-objects).


### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
