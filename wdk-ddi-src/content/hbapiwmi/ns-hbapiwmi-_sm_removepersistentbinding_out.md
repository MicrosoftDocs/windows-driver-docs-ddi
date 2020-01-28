---
UID: NS:hbapiwmi._SM_RemovePersistentBinding_OUT
title: _SM_RemovePersistentBinding_OUT (hbapiwmi.h)
description: The SM_REmovePersistentBinding_OUT structure is used to receive output parameters from the SM_RemovePersistentBinding method.
old-location: storage\sm_removepersistentbinding_out.htm
tech.root: storage
ms.assetid: 48d236c4-709d-4a4f-a730-df5f79787fe7
ms.date: 03/29/2018
ms.keywords: "*PSM_RemovePersistentBinding_OUT, PSM_RemovePersistentBinding_OUT, PSM_RemovePersistentBinding_OUT structure pointer [Storage Devices], SM_RemovePersistentBinding_OUT, SM_RemovePersistentBinding_OUT structure [Storage Devices], _SM_RemovePersistentBinding_OUT, hbapiwmi/PSM_RemovePersistentBinding_OUT, hbapiwmi/SM_RemovePersistentBinding_OUT, storage.sm_removepersistentbinding_out, structs-Fibre_e35eed9b-725a-4d27-90f9-9c40e49e9415.xml"
f1_keywords:
 - "hbapiwmi/SM_RemovePersistentBinding_OUT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- SM_RemovePersistentBinding_OUT
product:
- Windows
targetos: Windows
req.typenames: SM_RemovePersistentBinding_OUT, *PSM_RemovePersistentBinding_OUT
---

# _SM_RemovePersistentBinding_OUT structure


## -description


The SM_REmovePersistentBinding_OUT structure is used to receive output parameters from the SM_RemovePersistentBinding method.


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.


## -remarks



The WMI tool suite generates a declaration of the SM_RemovePersistentBinding_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



