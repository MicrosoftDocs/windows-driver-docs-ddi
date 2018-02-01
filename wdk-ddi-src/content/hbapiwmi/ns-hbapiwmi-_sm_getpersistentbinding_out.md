---
UID: NS:hbapiwmi._SM_GetPersistentBinding_OUT
title: "_SM_GetPersistentBinding_OUT"
author: windows-driver-content
description: The SM_GetPersistentBinding_OUT structure is used to receive output parameters from the SM_GetPersistentBinding method.
old-location: storage\sm_getpersistentbinding_out.htm
old-project: storage
ms.assetid: aa80e05c-e322-4350-80e7-28d53821c510
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: SM_GetPersistentBinding_OUT structure [Storage Devices], _SM_GetPersistentBinding_OUT, hbapiwmi/PSM_GetPersistentBinding_OUT, PSM_GetPersistentBinding_OUT structure pointer [Storage Devices], *PSM_GetPersistentBinding_OUT, structs-Fibre_51ba485a-c18a-4d45-a77a-859d55acc4c6.xml, storage.sm_getpersistentbinding_out, hbapiwmi/SM_GetPersistentBinding_OUT, PSM_GetPersistentBinding_OUT, SM_GetPersistentBinding_OUT
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
-	SM_GetPersistentBinding_OUT
product: Windows
targetos: Windows
req.typenames: SM_GetPersistentBinding_OUT, *PSM_GetPersistentBinding_OUT
---

# _SM_GetPersistentBinding_OUT structure


## -description


The SM_GetPersistentBinding_OUT structure is used to receive output parameters from the SM_GetPersistentBinding method.


## -syntax


````
typedef struct _SM_GetPersistentBinding_OUT {
  ULONG                 HBAStatus;
  ULONG                 TotalEntryCount;
  ULONG                 OutEntryCount;
  MS_SMHBA_BINDINGENTRY Entry[1];
} SM_GetPersistentBinding_OUT, *PSM_GetPersistentBinding_OUT;
````


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field TotalEntryCount

The total number of persistent bindings that are associated with the HBA.


### -field OutEntryCount

The total number of mappings that are retrieved. This value will be less than or equal to TotalEntryCount.


### -field Entry

An array of structures of type SMHBA_SCSIENTRY that describes an HBA's bindings between the operating system and the SAS identifiers.


## -remarks


The WMI tool suite generates a declaration of the SM_GetPersistentBinding_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.


