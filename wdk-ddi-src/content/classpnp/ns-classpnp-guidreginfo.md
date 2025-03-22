---
UID: NS:classpnp.GUIDREGINFO
tech.root: kernel
title: GUIDREGINFO
ms.date: 03/11/2024
targetos: Windows
description: 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: classpnp.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: GUIDREGINFO, *PGUIDREGINFO
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - classpnp.h
api_name:
 - GUIDREGINFO
 - PGUIDREGINFO
f1_keywords:
 - GUIDREGINFO
 - classpnp/GUIDREGINFO
 - PGUIDREGINFO
 - classpnp/PGUIDREGINFO
dev_langs:
 - c++
helpviewer_keywords:
 - WMIREGINFO
---

# GUIDREGINFO structure (classpnp.h)

## -description

The **GUIDREGINFO** structure contains GUID registration information.

## -struct-fields

### -field Guid

Specifies the GUID to register.

### -field InstanceCount

Specifies the count of instances of data block.

### -field Flags

Additional flags, for more information see the **[WMIREGINFOW](../wmistr/ns-wmistr-wmireginfow.md)** structure (wmistr.h).

## -remarks

## -see-also

- **[WMIREGINFOW](../wmistr/ns-wmistr-wmireginfow.md)**
