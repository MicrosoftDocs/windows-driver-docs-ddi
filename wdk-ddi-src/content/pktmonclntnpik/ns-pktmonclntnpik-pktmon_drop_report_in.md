---
UID: NS:pktmonclntnpik._PKTMON_DROP_REPORT_IN
tech.root: netvista
title: PKTMON_DROP_REPORT_IN
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_DROP_REPORT_IN structure contains information about why and where a packet was dropped in the network stack.
ai-usage: ai-assisted
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_DROP_REPORT_IN
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntnpik.h
api_name:
 - _PKTMON_DROP_REPORT_IN
 - PKTMON_DROP_REPORT_IN
f1_keywords:
 - _PKTMON_DROP_REPORT_IN
 - pktmonclntnpik/_PKTMON_DROP_REPORT_IN
 - PKTMON_DROP_REPORT_IN
 - pktmonclntnpik/PKTMON_DROP_REPORT_IN
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_DROP_REPORT_IN
---

## -description

The **PKTMON_DROP_REPORT_IN** structure contains information about why and where a packet was dropped in the network stack. This structure is passed to the **[PKTMON_PROVIDER_PACKET_DROP](nc-pktmonclntnpik-pktmon_provider_packet_drop.md)** callback when reporting packet drop events.

## -struct-fields

### -field Header

A [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header.md) structure used for versioning and size validation.

### -field DropReason

A 32-bit value indicating the reason code for why the packet was dropped. The interpretation of this code is component-specific and provides diagnostic information about the drop cause.

### -field LocationCode

A 32-bit value indicating the location code where the packet was dropped. This helps identify the specific point in the component's processing path where the drop occurred.

## -remarks

Components use this structure when calling **[PktMonClntNblDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntnbldrop.md)** or **[PktMonClntHeaderInfoDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfodrop.md)** to provide detailed diagnostic information about packet drops.

## -see-also

- [PKTMON_PROVIDER_PACKET_DROP](nc-pktmonclntnpik-pktmon_provider_packet_drop.md)
- [PktMonClntNblDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntnbldrop.md)
- [PktMonClntHeaderInfoDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfodrop.md)

