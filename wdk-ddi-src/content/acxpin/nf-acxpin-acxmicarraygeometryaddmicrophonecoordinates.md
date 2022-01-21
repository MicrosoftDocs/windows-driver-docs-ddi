---
UID: NF:acxpin.AcxMicArrayGeometryAddMicrophoneCoordinates
tech.root: audio
title: AcxMicArrayGeometryAddMicrophoneCoordinates
ms.date: 01/21/2022
targetos: Windows
description: The AcxMicArrayGeometryAddMicrophoneCoordinates function adds physical coordinates to a microphone array geometry.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
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
 - acxpin.h
api_name:
 - AcxMicArrayGeometryAddMicrophoneCoordinates
f1_keywords:
 - AcxMicArrayGeometryAddMicrophoneCoordinates
 - acxpin/AcxMicArrayGeometryAddMicrophoneCoordinates
dev_langs:
 - c++
---

## -description

The **AcxMicArrayGeometryAddMicrophoneCoordinates** function adds physical coordinates to a microphone array geometry.

## -parameters

### -param MicArrayGeometry [in]

The microphone array geometry to which the new coordinates are to be added.

### -param MicrophoneCoordinates [in]

The microphone coordinates to add to the microphone array geometry.

### -param MicrophoneCoordinatesCount [in]

The number of coordinates to add.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

## -see-also

- [ACXMICARRAYGEOMETRY](ns-acxpin-acx_mic_array_geometry.md)
- [ACX_MICROPHONE_COORDINATES](ns-acxpin-acx_microphone_coordinates.md)
