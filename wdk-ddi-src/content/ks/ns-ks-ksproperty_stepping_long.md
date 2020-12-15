---
UID: NS:ks.__unnamed_struct_11
title: KSPROPERTY_STEPPING_LONG (ks.h)
description: The KSPROPERTY_STEPPING_LONG structure defines the valid range of values for a 32-bit property.
old-location: stream\ksproperty_stepping_long.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSPROPERTY_STEPPING_LONG structure"]
ms.keywords: "*PKSPROPERTY_STEPPING_LONG, KSPROPERTY_STEPPING_LONG, KSPROPERTY_STEPPING_LONG structure [Streaming Media Devices], PKSPROPERTY_STEPPING_LONG, PKSPROPERTY_STEPPING_LONG structure pointer [Streaming Media Devices], ks-struct_2aad8fb1-d35c-4227-ad97-92451261b33c.xml, ks/KSPROPERTY_STEPPING_LONG, ks/PKSPROPERTY_STEPPING_LONG, stream.ksproperty_stepping_long"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: KSPROPERTY_STEPPING_LONG, *PKSPROPERTY_STEPPING_LONG
f1_keywords:
 - PKSPROPERTY_STEPPING_LONG
 - ks/PKSPROPERTY_STEPPING_LONG
 - KSPROPERTY_STEPPING_LONG
 - ks/KSPROPERTY_STEPPING_LONG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSPROPERTY_STEPPING_LONG
---

# KSPROPERTY_STEPPING_LONG structure


## -description

The KSPROPERTY_STEPPING_LONG structure defines the valid range of values for a 32-bit property.

## -struct-fields

### -field SteppingDelta

Specifies the step value that should be used to create legal values within the range defined in <b>Bounds</b>.

### -field Reserved

Reserved for system use.

### -field Bounds

A structure of type <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_long">KSPROPERTY_BOUNDS_LONG</a> that specifies the range of values over which the <b>SteppingDelta</b> is valid.

## -remarks

The <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a> structure may contain structures of this type in its <b>Members</b> array.

See the Testcap sample in the Windows Driver Kit (WDK) for examples of usage.

For more information, see <a href="/windows-hardware/drivers/stream/ks-properties">KS Properties</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_long">KSPROPERTY_BOUNDS_LONG</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a>
