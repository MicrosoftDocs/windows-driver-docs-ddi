---
UID: NS:ks.__unnamed_struct_63
title: KSERROR (ks.h)
description: The KSERROR structure is used to report streaming errors in both kernel and user mode to their respective quality managers.
old-location: stream\kserror.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSERROR structure"]
ms.keywords: "*PKSERROR, KSERROR, KSERROR structure [Streaming Media Devices], PKSERROR, PKSERROR structure pointer [Streaming Media Devices], ks-struct_86211cee-a711-4a84-b8ea-6de2d9ef81f6.xml, ks/KSERROR, ks/PKSERROR, stream.kserror"
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
req.typenames: KSERROR, *PKSERROR
f1_keywords:
 - PKSERROR
 - ks/PKSERROR
 - KSERROR
 - ks/KSERROR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSERROR
---

# KSERROR structure


## -description

The KSERROR structure is used to report streaming errors in both kernel and user mode to their respective quality managers.

## -struct-fields

### -field Context

Specifies a context parameter that was originally passed to the connection.

### -field Status

Specifies the NTSTATUS error.

## -remarks

Streaming error notifications can be generated against the Quality Management sink, if assigned. The same method of proxying Quality Management complaints is used for forwarding error reports for DirectShow graphs. For more information, see <a href="/windows-hardware/drivers/stream/quality-management">Quality Management</a>.

## -see-also

<a href="/previous-versions/ff561671(v=vs.85)">KSDEGRADE</a>



<a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksdegrade_standard">KSDEGRADE_STANDARD</a>



<a href="/windows-hardware/drivers/stream/ksproperty-quality-error">KSPROPERTY_QUALITY_ERROR</a>
