---
UID: NF:acxpin.ACX_CONNECTION_INIT
tech.root: audio
title: ACX_CONNECTION_INIT
ms.date: 04/12/2022
targetos: Windows
description: Initializes an ACX_CONNECTION structure for use in configuring a connection.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.idl: 
req.include-header: 
req.irql: 
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
 - ACX_CONNECTION_INIT
f1_keywords:
 - ACX_CONNECTION_INIT
 - acxpin/ACX_CONNECTION_INIT
dev_langs:
 - c++
---

## -description

Initializes an [ACX_CONNECTION](ns-acxpin-acx_connection.md) structure for use in configuring a connection.

## -parameters

### -param Connection [out]

Pointer to an [ACX_CONNECTION](ns-acxpin-acx_connection.md) object to be initialized.

### -param FromObject [in]

The **ACXOBJECT** from which the connection starts.

### -param ToObject [in]

The **ACXOBJECT** to which the connection ends.

## -remarks

## -see-also

- [ACX_CONNECTION](ns-acxpin-acx_connection.md)
- [acxpin.h header](index.md)


