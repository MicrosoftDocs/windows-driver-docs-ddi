---
UID: NS:ks.__unnamed_struct_26
title: KSP_PIN
author: windows-driver-content
description: Kernel streaming clients use the KSP_PIN structure to specify the property and pin type within a KSPROPSETID_Pin property request.
old-location: stream\ksp_pin.htm
tech.root: stream
ms.assetid: 0be4c4e1-6ea6-4439-841d-088cb1902604
ms.date: 04/23/2018
ms.keywords: "*PKSP_PIN, KSPROPERTY_PIN_FLAGS_ATTRIBUTE_RANGE_AWARE, KSP_PIN, KSP_PIN structure [Streaming Media Devices], PKSP_PIN, PKSP_PIN structure pointer [Streaming Media Devices], ks-struct_02faf16f-fb8d-4f1f-9176-e2c379a36d4e.xml, ks/KSP_PIN, ks/PKSP_PIN, stream.ksp_pin"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSP_PIN
product:
- Windows
targetos: Windows
req.typenames: KSP_PIN, *PKSP_PIN
---

# KSP_PIN structure


## -description


Kernel streaming clients use the KSP_PIN structure to specify the property and pin type within a KSPROPSETID_Pin property request.


## -struct-fields




### -field Property

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure.


### -field PinId

Specifies the pin type ID.


### -field Reserved

Reserved. Should be set to zero.

Reserved. Should be set to zero.


### -field Flags

Pin flags. This is set to either 0 or the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_PIN_FLAGS_ATTRIBUTE_RANGE_AWARE"></a><a id="ksproperty_pin_flags_attribute_range_aware"></a><dl>
<dt><b>KSPROPERTY_PIN_FLAGS_ATTRIBUTE_RANGE_AWARE</b></dt>
</dl>
</td>
<td width="60%">
The client is aware of attributes and handles attribute ranges.

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>
 

 

