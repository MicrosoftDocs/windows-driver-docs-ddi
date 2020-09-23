---
UID: NS:ks.__unnamed_struct_58
title: KSCLOCK_CREATE (ks.h)
description: The KSCLOCK_CREATE structure is used in clock create parameters for the KsCreateClock function.
old-location: stream\ksclock_create.htm
tech.root: stream
ms.assetid: 72986a01-de40-4b8f-9dfc-d26f4999e66b
ms.date: 04/23/2018
keywords: ["KSCLOCK_CREATE structure"]
ms.keywords: "*PKSCLOCK_CREATE, KSCLOCK_CREATE, KSCLOCK_CREATE structure [Streaming Media Devices], PKSCLOCK_CREATE, PKSCLOCK_CREATE structure pointer [Streaming Media Devices], ks-struct_8202019a-97e5-4d76-9594-93189e3c1c30.xml, ks/KSCLOCK_CREATE, ks/PKSCLOCK_CREATE, stream.ksclock_create"
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
req.typenames: KSCLOCK_CREATE, *PKSCLOCK_CREATE
f1_keywords:
 - PKSCLOCK_CREATE
 - ks/PKSCLOCK_CREATE
 - KSCLOCK_CREATE
 - ks/KSCLOCK_CREATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSCLOCK_CREATE
---

# KSCLOCK_CREATE structure


## -description

The KSCLOCK_CREATE structure is used in clock create parameters for the <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscreateclock">KsCreateClock</a> function.

## -struct-fields

### -field CreateFlags

Currently consists of a flags item, which must be set to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscreateclock">KsCreateClock</a>