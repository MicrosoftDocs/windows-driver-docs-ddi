---
UID: NS:pktmonnpik._PKTMON_HEADER
tech.root: netvista
title: PKTMON_HEADER
ms.date: 02/19/2025
targetos: Windows
description: The PKTMON_HEADER struct is a common header for version control.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_HEADER
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonnpik.h
api_name:
 - _PKTMON_HEADER
 - PKTMON_HEADER
f1_keywords:
 - _PKTMON_HEADER
 - pktmonnpik/_PKTMON_HEADER
 - PKTMON_HEADER
 - pktmonnpik/PKTMON_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_HEADER
---

## -description

The **PKTMON_HEADER** struct is a common header for version control.

## -struct-fields

### -field Size

Should contain the size of structure **[PKTMON_PACKET_CONTEXT_IN](ns-pktmonnpik-pktmon_packet_context_in.md)**.

### -field Version

Contains the version being used.

## -remarks

Currently only version 0 is supported.

### -see-also

- **[PKTMON_PACKET_CONTEXT_IN](ns-pktmonnpik-pktmon_packet_context_in.md)**
- **[PktMonClntHeaderInfoLog](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfolog.md)**
- **[PktMonClntHeaderInfoDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfodrop.md)**
