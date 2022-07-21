---
UID: NS:acxstreams._ACXDRMRIGHTS
tech.root: audio
title: ACXDRMRIGHTS
ms.date: 06/22/2021
targetos: Windows
description: The ACXDRMRIGHTS structure specifies the DRM content rights assigned to a KS audio pin or to a driver's stream object.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACXDRMRIGHTS, *PACXDRMRIGHTS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - _ACXDRMRIGHTS
 - PACXDRMRIGHTS
 - ACXDRMRIGHTS
f1_keywords:
 - _ACXDRMRIGHTS
 - acxstreams/_ACXDRMRIGHTS
 - PACXDRMRIGHTS
 - acxstreams/PACXDRMRIGHTS
 - ACXDRMRIGHTS
 - acxstreams/ACXDRMRIGHTS
dev_langs:
 - c++
---

## -description

The ACXDRMRIGHTS structure specifies the DRM content rights assigned to a KS audio pin or to a driver's stream object.

## -struct-fields

### -field CopyProtect

Specifies one of the following copy-protection values: 

**TRUE**  Enables copy protection. 

An audio application must not do the following: 

- Store the content in any form in any nonvolatile storage.

- Pass the content by reference or by value to any other component within the host system that is not authenticated by the DRM system.

**FALSE** Disables copy protection. Content can be copied without restrictions.

### -field Reserved

Reserved for future use. Initialize to zero.

### -field DigitalOutputDisable

Specifies one of the following digital output protection values:

**TRUE**  Disable digital outputs. A software component must not transfer the content out of the host system through any type of digital interface. Note that digital output protection does not affect USB devices because the host system includes USB devices.

**FALSE**  Enables digital outputs. Content can be transferred from the host system to an external component without restrictions.

## -remarks

If the driver supports DRMRIGHTS and also implements a proprietary copy protection mechanism, the driver must aggregate the result of the proprietary implementation with the values of CopyProtect and DigitalOutputDisable to determine the final copy protection state. The final copy protection state must be the most restrictive of all outstanding copy protection requests.

## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic