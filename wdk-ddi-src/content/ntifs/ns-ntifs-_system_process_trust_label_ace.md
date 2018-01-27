---
UID: NS:ntifs._SYSTEM_PROCESS_TRUST_LABEL_ACE
title: _SYSTEM_PROCESS_TRUST_LABEL_ACE
author: windows-driver-content
description: Reserved.
old-location: ifsk\system_process_trust_label_ace.htm
old-project: ifsk
ms.assetid: DF334754-8027-418D-B329-877492896B82
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/SYSTEM_PROCESS_TRUST_LABEL_ACE, ifsk.system_process_trust_label_ace, SYSTEM_PROCESS_TRUST_LABEL_ACE structure [Installable File System Drivers], SYSTEM_PROCESS_TRUST_LABEL_ACE, *PSYSTEM_PROCESS_TRUST_LABEL_ACE, _SYSTEM_PROCESS_TRUST_LABEL_ACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
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
-	Ntifs.h
apiname: 
-	SYSTEM_PROCESS_TRUST_LABEL_ACE
product: Windows
targetos: Windows
req.typenames: *PSYSTEM_PROCESS_TRUST_LABEL_ACE, SYSTEM_PROCESS_TRUST_LABEL_ACE
---

# _SYSTEM_PROCESS_TRUST_LABEL_ACE structure


## -description


Reserved.


## -syntax


````
struct SYSTEM_PROCESS_TRUST_LABEL_ACE {
  ACE_HEADER  Header;
  ACCESS_MASK Mask;
  ULONG       SidStart;
};
````


## -struct-fields




### -field Header



### -field Mask



### -field SidStart


