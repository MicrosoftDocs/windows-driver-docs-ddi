---
UID: NE:ntddrilapitypes.RILCALLMODIFICATIONCAUSECODE
title: RILCALLMODIFICATIONCAUSECODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationcausecode.htm
old-project: netvista
ms.assetid: d2785ee2-6e5d-474e-9d0f-57da956b6ec7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcallmodificationcausecode, RILCALLMODIFICATIONCAUSECODE, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, ntddrilapitypes/RILCALLMODIFICATIONCAUSECODE, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, RILCALLMODIFICATIONCAUSECODE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, *LPRILCALLMODIFICATIONCAUSECODE, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_MAX, RIL_CALL_MODIFIED_CAUSE_MAX, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, ntddrilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILCALLMODIFICATIONCAUSECODE
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLMODIFICATIONCAUSECODE, RILCALLMODIFICATIONCAUSECODE"
---

# RILCALLMODIFICATIONCAUSECODE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILCALLMODIFICATIONCAUSECODE { 
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC,
  RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR,
  RIL_CALL_MODIFIED_CAUSE_MAX
} RILCALLMODIFICATIONCAUSECODE;
````


## -enum-fields




### -field RIL_CALL_MODIFIED_CAUSE_NONE



### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT



### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS



### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS



### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT



### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION



### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC



### -field RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR



### -field RIL_CALL_MODIFIED_CAUSE_MAX


