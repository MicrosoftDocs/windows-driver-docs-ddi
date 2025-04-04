---
UID: NA:pktmonclntk
tech.root: netvista
title: Pktmonclntk.h header
ms.date: 03/14/2025
targetos: Windows
description: Defines public data types and functions used by drivers to publish network packets into the pktmon diagnostics framework.
prerelease: false
req.assembly: 
req.construct-type: apiset
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
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
req.typenames: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - pktmonclntk
f1_keywords:
 - pktmonclntk
 - pktmonclntk/pktmonclntk
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - pktmonclntk
---

## -description

The pktmonclntk.h header file defines public data types and functions used by drivers to publish network packets into the pktmon diagnostics framework.

## -remarks

Kernel-mode Pktmon DDIs allow drivers to report network packet flow and drop information for packets traversing non-Microsoft drivers. Pktmon DDIs are especially useful for diagnosing issues like network connectivity and performance.

## -see-also

- [Pktmonnpik.h header](../pktmonnpik/index.md)
- [Pktmondefk.h header](../pktmondefk/index.md)

## -examples
