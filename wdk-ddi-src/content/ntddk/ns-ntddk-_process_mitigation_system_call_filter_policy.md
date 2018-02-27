---
UID: NS:ntddk._PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY
title: "_PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY"
author: windows-driver-content
description: This structure is not supported.
old-location: kernel\process_mitigation_system_call_filter_policy.htm
old-project: kernel
ms.assetid: 6a64ae8d-43e3-4ebd-b10b-2ae8e607071f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY, PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY, PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY structure [Kernel-Mode Driver Architecture], _PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY, kernel.process_mitigation_system_call_filter_policy, ntddk/PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY
product: Windows
targetos: Windows
req.typenames: PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY, *PPROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY
---

# _PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY structure


## -description


This structure is not supported. 


## -syntax


````
typedef struct _PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY {
  union {
    ULONG Flags;
    struct {
      ULONG FilterId  :4;
      ULONG ReservedFlags  :28;
    } DUMMYSTRUCTNAME;
  } DUMMYUNIONNAME;
} PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY, PROCESS_MITIGATION_SYSTEM_CALL_FILTER_POLICY;
````


## -struct-fields




### -field DUMMYUNIONNAME


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.FilterId

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ReservedFlags

Reserved.

