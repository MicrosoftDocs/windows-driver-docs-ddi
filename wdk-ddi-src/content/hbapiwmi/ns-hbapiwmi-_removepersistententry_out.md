---
UID: NS:hbapiwmi._RemovePersistentEntry_OUT
title: _RemovePersistentEntry_OUT (hbapiwmi.h)
description: The RemovePersistentEntry_OUT structure is used to report the output parameter data of the RemovePersistentEntry WMI method to the WMI client.
old-location: storage\removepersistententry_out.htm
tech.root: storage
ms.assetid: 2fa578f7-5892-4ec1-a01f-49c828bd6913
ms.date: 03/29/2018
keywords: ["RemovePersistentEntry_OUT structure"]
ms.keywords: "*PRemovePersistentEntry_OUT, PRemovePersistentEntry_OUT, PRemovePersistentEntry_OUT structure pointer [Storage Devices], RemovePersistentEntry_OUT, RemovePersistentEntry_OUT structure [Storage Devices], _RemovePersistentEntry_OUT, hbapiwmi/PRemovePersistentEntry_OUT, hbapiwmi/RemovePersistentEntry_OUT, storage.removepersistententry_out, structs-Fibre_8a84bc15-be90-4a74-a551-c3cf43d4f5ef.xml"
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
targetos: Windows
req.typenames: RemovePersistentEntry_OUT, *PRemovePersistentEntry_OUT
f1_keywords:
 - _RemovePersistentEntry_OUT
 - hbapiwmi/_RemovePersistentEntry_OUT
 - PRemovePersistentEntry_OUT
 - hbapiwmi/PRemovePersistentEntry_OUT
 - RemovePersistentEntry_OUT
 - hbapiwmi/RemovePersistentEntry_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - RemovePersistentEntry_OUT
---

# _RemovePersistentEntry_OUT structure


## -description

The RemovePersistentEntry_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removepersistententry">RemovePersistentEntry</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -remarks

The WMI tool suite generates a declaration of the RemovePersistentEntry_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removepersistententry">RemovePersistentEntry</a>

