---
UID: NS:ksmedia._KS_COPY_MACROVISION
title: _KS_COPY_MACROVISION (ksmedia.h)
description: The KS_COPY_MACROVISION structure specifies the Macrovision level of the data stream.
tech.root: stream
ms.date: 03/10/2023
keywords: ["KS_COPY_MACROVISION structure"]
ms.keywords: "*PKS_COPY_MACROVISION, KS_COPY_MACROVISION, KS_COPY_MACROVISION structure [Streaming Media Devices], PKS_COPY_MACROVISION, PKS_COPY_MACROVISION structure pointer [Streaming Media Devices], _KS_COPY_MACROVISION, dvdref_42184498-7ac6-48d2-9f26-5bf69ececabb.xml, ksmedia/KS_COPY_MACROVISION, ksmedia/PKS_COPY_MACROVISION, stream.ks_copy_macrovision"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
req.typenames: KS_COPY_MACROVISION, *PKS_COPY_MACROVISION
f1_keywords:
 - _KS_COPY_MACROVISION
 - ksmedia/_KS_COPY_MACROVISION
 - PKS_COPY_MACROVISION
 - ksmedia/PKS_COPY_MACROVISION
 - KS_COPY_MACROVISION
 - ksmedia/KS_COPY_MACROVISION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - _KS_COPY_MACROVISION
 - PKS_COPY_MACROVISION
 - KS_COPY_MACROVISION
---

## -description

The **KS_COPY_MACROVISION** structure specifies the Macrovision level of the data stream.

## -struct-fields

### -field MACROVISIONLevel

Specifies the Macrovision level. This must be one of the following values from the **KS_COPY_MACROVISION_LEVEL** enumeration:

| Level | Meaning |
|---|---|
| KS_MACROVISION_DISABLED | Indicates that Macrovision copyright protection should not be in effect. |
| KS_MACROVISION_LEVEL1 | Indicates that Macrovision level 1 copyright protection must be in effect. |
| KS_MACROVISION_LEVEL2 | Indicates that Macrovision level 2 copyright protection must be in effect. |
| KS_MACROVISION_LEVEL3 | Indicates that Macrovision level 3 copyright protection must be in effect. |

## -remarks

The KS_COPY_MACROVISION structure is used by the KSPROPERTY_COPY_MACROVISION property.

For additional uses of this structure see [DVD Copyright Protection](/windows-hardware/drivers/stream/dvd-copyright-protection) and [Macrovision](/windows-hardware/drivers/stream/macrovision).

## -see-also

[KSPROPERTY_COPY_MACROVISION](/windows-hardware/drivers/stream/ksproperty-copy-macrovision)
