---
UID: NS:ks.__unnamed_struct_12
title: KSPROPERTY_STEPPING_LONGLONG (ks.h)
description: The KSPROPERTY_STEPPING_LONGLONG structure defines the valid range of values for a 64-bit property.
old-location: stream\ksproperty_stepping_longlong.htm
tech.root: stream
ms.assetid: 14ec504e-baf6-441a-b908-2d8c051dd45a
ms.date: 04/23/2018
ms.keywords: "*PKSPROPERTY_STEPPING_LONGLONG, KSPROPERTY_STEPPING_LONGLONG, KSPROPERTY_STEPPING_LONGLONG structure [Streaming Media Devices], PKSPROPERTY_STEPPING_LONGLONG, PKSPROPERTY_STEPPING_LONGLONG structure pointer [Streaming Media Devices], ks-struct_f7cc7036-e7b5-4765-bf2e-abd24f5f06a6.xml, ks/KSPROPERTY_STEPPING_LONGLONG, ks/PKSPROPERTY_STEPPING_LONGLONG, stream.ksproperty_stepping_longlong"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSPROPERTY_STEPPING_LONGLONG
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_STEPPING_LONGLONG, *PKSPROPERTY_STEPPING_LONGLONG
---

# KSPROPERTY_STEPPING_LONGLONG structure


## -description


The KSPROPERTY_STEPPING_LONGLONG structure defines the valid range of values for a 64-bit property.


## -struct-fields




### -field SteppingDelta

Specifies the step value that should be used to create legal values within the range defined in <b>Bounds</b>.


### -field Bounds

Specifies a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_bounds_longlong">KSPROPERTY_BOUNDS_LONGLONG</a> that specifies the range of values over which the <b>SteppingDelta</b> is valid.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a> structure may contain structures of this type in its <b>Members</b> array.

See the Testcap sample in the Windows Driver Kit (WDK) for examples of usage.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-properties">KS Properties</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_bounds_longlong">KSPROPERTY_BOUNDS_LONGLONG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_memberslist">KSPROPERTY_MEMBERSLIST</a>
 

 

