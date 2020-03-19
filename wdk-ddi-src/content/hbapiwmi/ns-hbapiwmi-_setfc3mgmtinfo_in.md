---
UID: NS:hbapiwmi._SetFC3MgmtInfo_IN
title: _SetFC3MgmtInfo_IN (hbapiwmi.h)
description: The SetFC3MgmtInfo_IN structure is used to deliver input parameter data to the SetFC3MgmtInfo WMI method.
old-location: storage\setfc3mgmtinfo_in.htm
tech.root: storage
ms.assetid: 2ad51d73-67f3-4ce0-b7e1-6bdc1b7e3b0c
ms.date: 03/29/2018
keywords: ["_SetFC3MgmtInfo_IN structure"]
ms.keywords: "*PSetFC3MgmtInfo_IN, PSetFC3MgmtInfo_IN, PSetFC3MgmtInfo_IN structure pointer [Storage Devices], SetFC3MgmtInfo_IN, SetFC3MgmtInfo_IN structure [Storage Devices], _SetFC3MgmtInfo_IN, hbapiwmi/PSetFC3MgmtInfo_IN, hbapiwmi/SetFC3MgmtInfo_IN, storage.setfc3mgmtinfo_in, structs-Fibre_d4b69005-dc94-411f-810a-6767699e0b11.xml"
f1_keywords:
 - "hbapiwmi/SetFC3MgmtInfo_IN"
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
- SetFC3MgmtInfo_IN
product:
- Windows
targetos: Windows
req.typenames: SetFC3MgmtInfo_IN, *PSetFC3MgmtInfo_IN
---

# _SetFC3MgmtInfo_IN structure


## -description


The SetFC3MgmtInfo_IN structure is used to deliver input parameter data to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setfc3mgmtinfo">SetFC3MgmtInfo</a> WMI method.


## -struct-fields




### -field MgmtInfo

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafc3mgmtinfo">HBAFC3MgmtInfo</a> that holds FC3 management information that will be used to configure the fibre channel adapter. 


## -remarks



The WMI tool suite generates a declaration of the SetFC3MgmtInfo_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setfc3mgmtinfo">SetFC3MgmtInfo</a>
 

 

