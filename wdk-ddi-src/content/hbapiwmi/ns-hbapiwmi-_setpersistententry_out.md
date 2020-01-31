---
UID: NS:hbapiwmi._SetPersistentEntry_OUT
title: _SetPersistentEntry_OUT (hbapiwmi.h)
description: The SetPersistentEntry_OUT structure is used to report the output parameter data of the SetPersistentEntry WMI method to the WMI client.
old-location: storage\setpersistententry_out.htm
tech.root: storage
ms.assetid: c2089ae9-e872-4bbb-8e7b-fe11082d2b46
ms.date: 03/29/2018
ms.keywords: "*PSetPersistentEntry_OUT, PSetPersistentEntry_OUT, PSetPersistentEntry_OUT structure pointer [Storage Devices], SetPersistentEntry_OUT, SetPersistentEntry_OUT structure [Storage Devices], _SetPersistentEntry_OUT, hbapiwmi/PSetPersistentEntry_OUT, hbapiwmi/SetPersistentEntry_OUT, storage.setpersistententry_out, structs-Fibre_3dbfc9dd-6c90-4908-bb5d-c331a2e0334c.xml"
f1_keywords:
 - "hbapiwmi/SetPersistentEntry_OUT"
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
- SetPersistentEntry_OUT
product:
- Windows
targetos: Windows
req.typenames: SetPersistentEntry_OUT, *PSetPersistentEntry_OUT
---

# _SetPersistentEntry_OUT structure


## -description


The SetPersistentEntry_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setpersistententry">SetPersistentEntry</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>. 


## -remarks



The WMI tool suite generates a declaration of the SetPersistentEntry_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setpersistententry">SetPersistentEntry</a>
 

 

