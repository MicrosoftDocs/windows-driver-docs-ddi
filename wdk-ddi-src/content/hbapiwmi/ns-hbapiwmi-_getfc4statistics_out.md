---
UID: NS:hbapiwmi._GetFC4Statistics_OUT
title: _GetFC4Statistics_OUT (hbapiwmi.h)
description: The GetFC4Statistics_OUT structure is used to report the output parameter data of the GetFC4Statistics WMI method to the WMI client.
old-location: storage\getfc4statistics_out.htm
tech.root: storage
ms.assetid: fc747ff1-cc84-4863-a66a-ae172f45f2bd
ms.date: 03/29/2018
ms.keywords: "*PGetFC4Statistics_OUT, GetFC4Statistics_OUT, GetFC4Statistics_OUT structure [Storage Devices], PGetFC4Statistics_OUT, PGetFC4Statistics_OUT structure pointer [Storage Devices], _GetFC4Statistics_OUT, hbapiwmi/GetFC4Statistics_OUT, hbapiwmi/PGetFC4Statistics_OUT, storage.getfc4statistics_out, structs-Fibre_2a49fe85-534d-42df-8d8f-d07d0c4a7193.xml"
ms.topic: struct
f1_keywords:
 - "hbapiwmi/GetFC4Statistics_OUT"
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
- GetFC4Statistics_OUT
product:
- Windows
targetos: Windows
req.typenames: GetFC4Statistics_OUT, *PGetFC4Statistics_OUT
---

# _GetFC4Statistics_OUT structure


## -description


The GetFC4Statistics_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc4statistics">GetFC4Statistics</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a> that indicates the result of an HBA query operation.


### -field FC4Statistics

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_msfc_fc4statistics">MSFC_FC4STATISTICS</a> that holds statistics for the specified FC-4 protocol. 


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc4statistics">GetFC4Statistics</a> WMI method reports traffic statistics for a specific FC-4 protocol via a specific local HBA and port of type Nx_Port.

The WMI tool suite generates a declaration of the GetFC4Statistics_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc4statistics">GetFC4Statistics</a>
 

 

