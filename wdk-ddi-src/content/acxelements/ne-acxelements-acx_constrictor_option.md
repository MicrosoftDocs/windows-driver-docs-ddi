---
UID: NE:acxelements._ACX_CONSTRICTOR_OPTION
tech.root: audio 
title: ACX_CONSTRICTOR_OPTION
ms.date: 04/29/2022
targetos: Windows
description: The ACX_CONSTRICTOR_OPTION enumeration defines the options for the loopback protection status of a stream audio engine node.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxelements.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_CONSTRICTOR_OPTION
 - ACX_CONSTRICTOR_OPTION
f1_keywords:
 - _ACX_CONSTRICTOR_OPTION
 - acxelements/_ACX_CONSTRICTOR_OPTION
 - ACX_CONSTRICTOR_OPTION
 - acxelements/ACX_CONSTRICTOR_OPTION
dev_langs:
 - c++
---

## -description

The **ACX_CONSTRICTOR_OPTION** enumeration defines the options for the loopback protection status of a stream audio engine node.

## -enum-fields

### -field AcxConstrictorOptionNone

This is the default state for the loopback protection status of a stream. When all active streams are in this state it indicates that the loopback tap contains meaningful data. 

### -field AcxConstrictorOptionMute

When an active stream is in this state it indicates that the loopback tap for the audio output will emit silence. 

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)


