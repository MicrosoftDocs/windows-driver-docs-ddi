---
UID: NS:hbapiwmi._SM_GetPersistentBinding_IN
title: "_SM_GetPersistentBinding_IN"
author: windows-driver-content
description: The SM_GetPersistentBinding_IN structure is used to provide input parameters to the SM_GetPersistentBinding method.
old-location: storage\sm_getpersistentbinding_in.htm
old-project: storage
ms.assetid: 6c716394-1e82-40d2-befc-50a0ea88f750
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PSM_GetPersistentBinding_IN, ,, B, G, I, M, N, P, PSM_GetPersistentBinding_IN, PSM_GetPersistentBinding_IN structure pointer [Storage Devices], S, SM_GetPersistentBinding_IN, SM_GetPersistentBinding_IN structure [Storage Devices], _, _SM_GetPersistentBinding_IN, d, e, g, hbapiwmi/PSM_GetPersistentBinding_IN, hbapiwmi/SM_GetPersistentBinding_IN, i, n, r, s, storage.sm_getpersistentbinding_in, structs-Fibre_2cf97173-2aa3-4770-865a-825f5db0daf1.xml, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
apiname:
-	SM_GetPersistentBinding_IN
product: Windows
targetos: Windows
req.typenames: SM_GetPersistentBinding_IN, *PSM_GetPersistentBinding_IN
---

# _SM_GetPersistentBinding_IN structure


## -description


The SM_GetPersistentBinding_IN structure is used to provide input parameters to the SM_GetPersistentBinding method.


## -syntax


````
typedef struct _SM_GetPersistentBinding_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DomainPortWWN[8];
  ULONG InEntryCount;
} SM_GetPersistentBinding_IN, *PSM_GetPersistentBinding_IN;
````


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field InEntryCount

The number of persistent bindings that are associated with the HBA.


## -remarks



The WMI tool suite generates a declaration of the SM_GetPersistentBinding_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



