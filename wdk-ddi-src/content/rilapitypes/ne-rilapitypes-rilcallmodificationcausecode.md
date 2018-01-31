---
UID: NE:rilapitypes.RILCALLMODIFICATIONCAUSECODE
title: RILCALLMODIFICATIONCAUSECODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationcausecode_2.htm
old-project: netvista
ms.assetid: 44309e4e-a0a0-4aed-b942-2d15b8ab07dc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLMODIFICATIONCAUSECODE enumeration [Network Drivers Starting with Windows Vista], RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, netvista.rilcallmodificationcausecode_2, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS, *LPRILCALLMODIFICATIONCAUSECODE, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS, rilapitypes/RILCALLMODIFICATIONCAUSECODE, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION, RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR, rilapitypes/RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT, RILCALLMODIFICATIONCAUSECODE, rilapitypes/RIL_CALL_MODIFIED_CAUSE_MAX, RIL_CALL_MODIFIED_CAUSE_MAX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILCALLMODIFICATIONCAUSECODE
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLMODIFICATIONCAUSECODE, RILCALLMODIFICATIONCAUSECODE"
req.product: Windows 10 or later.
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



#### - RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_RTP_TIMEOUT



#### - RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_QOS



#### - RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_PACKET_LOSS



#### - RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LOW_THROUGHPUT



#### - RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_THERMAL_MITIGATION



#### - RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_LIPSYNC



#### - RIL_CALL_MODIFIED_CAUSE_DOWNGRADE_GENERIC_ERROR



#### - RIL_CALL_MODIFIED_CAUSE_MAX


