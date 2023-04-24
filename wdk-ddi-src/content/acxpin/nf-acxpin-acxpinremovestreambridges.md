---
UID: NF:acxpin.AcxPinRemoveStreamBridges
tech.root: audio
title: AcxPinRemoveStreamBridges
ms.date: 12/16/2022
targetos: Windows
description: The AcxPinRemoveStreamBridges function removes ACXSTREAMBRIDGE objects from the specified pin.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
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
 - acxpin.h
api_name:
 - AcxPinRemoveStreamBridges
f1_keywords:
 - AcxPinRemoveStreamBridges
 - acxpin/AcxPinRemoveStreamBridges
dev_langs:
 - c++
---

## -description

The **AcxPinRemoveStreamBridges** function removes ACXSTREAMBRIDGE objects from the specified pin.

## -parameters

### -param Pin [in]

The ACXPIN handle from which to remove the stream bridges.

### -param StreamBridges [in, reads(StreamBridgesCount)]

A pointer to an array of ACXSTREAMBRIDGE handles representing the steam bridges to remove from the *Pin*.

### -param StreamBridgesCount

The number of steam bridges to remove from the *Pin*. This parameter must not equal zero.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxpin.h header\]\(index.md\)
