---
UID: NS:hbapiwmi._SM_SetPersistentBinding_IN
title: "_SM_SetPersistentBinding_IN"
author: windows-driver-content
description: The SM_SetPersistentBinding_IN structure is used to provide input parameters to the SM_SetPersistentBinding method.
old-location: storage\sm_setpersistentbinding_in.htm
old-project: storage
ms.assetid: 33a8c609-aa65-4629-b4ee-3723e614d400
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbapiwmi/PSM_SetPersistentBinding_IN, hbapiwmi/SM_SetPersistentBinding_IN, PSM_SetPersistentBinding_IN, SM_SetPersistentBinding_IN structure [Storage Devices], PSM_SetPersistentBinding_IN structure pointer [Storage Devices], _SM_SetPersistentBinding_IN, storage.sm_setpersistentbinding_in, SM_SetPersistentBinding_IN, *PSM_SetPersistentBinding_IN, structs-Fibre_9af25c8f-f9de-482d-8103-f372405d7771.xml
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
-	SM_SetPersistentBinding_IN
product: Windows
targetos: Windows
req.typenames: SM_SetPersistentBinding_IN, *PSM_SetPersistentBinding_IN
---

# _SM_SetPersistentBinding_IN structure


## -description


The SM_SetPersistentBinding_IN structure is used to provide input parameters to the SM_SetPersistentBinding method.


## -syntax


````
typedef struct _SM_SetPersistentBinding_IN {
  UCHAR                 HbaPortWWN[8];
  UCHAR                 DomainPortWWN[8];
  ULONG                 InEntryCount;
  MS_SMHBA_BINDINGENTRY Entry[1];
} SM_SetPersistentBinding_IN, *PSM_SetPersistentBinding_IN;
````


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field InEntryCount

The number of persistent bindings that are associated with the HBA.


### -field Entry

A list of MS_SMHBA_BINDINGENTRY types for persistent binding.


## -remarks


The WMI tool suite generates a declaration of the SM_SetPersistentBinding_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.


