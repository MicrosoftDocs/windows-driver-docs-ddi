---
UID: NS:hbapiwmi._GetFcpTargetMapping_OUT
title: _GetFcpTargetMapping_OUT (hbapiwmi.h)
description: The GetFcpTargetMapping_OUT structure is used to report the output parameter data of the GetFcpTargetMapping WMI method to the WMI client.
old-location: storage\getfcptargetmapping_out.htm
tech.root: storage
ms.assetid: a3a3050a-6fa2-4ace-87f2-41b8364f4d30
ms.date: 03/29/2018
keywords: ["_GetFcpTargetMapping_OUT structure"]
ms.keywords: "*PGetFcpTargetMapping_OUT, GetFcpTargetMapping_OUT, GetFcpTargetMapping_OUT structure [Storage Devices], PGetFcpTargetMapping_OUT, PGetFcpTargetMapping_OUT structure pointer [Storage Devices], _GetFcpTargetMapping_OUT, hbapiwmi/GetFcpTargetMapping_OUT, hbapiwmi/PGetFcpTargetMapping_OUT, storage.getfcptargetmapping_out, structs-Fibre_ab6aca55-bb7c-4983-863c-de94e835a600.xml"
f1_keywords:
 - "hbapiwmi/GetFcpTargetMapping_OUT"
 - "GetFcpTargetMapping_OUT"
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
- GetFcpTargetMapping_OUT
product:
- Windows
targetos: Windows
req.typenames: GetFcpTargetMapping_OUT, *PGetFcpTargetMapping_OUT
---

# _GetFcpTargetMapping_OUT structure


## -description


The GetFcpTargetMapping_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a> WMI method to the WMI client. 


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>. 


### -field TotalEntryCount

Indicates the total number of persistent bindings associated with the HBA..


### -field OutEntryCount

Indicates the total number of mappings retrieved by the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a> WMI method. This value will be less than or equal to <b>TotalEntryCount</b>. 


### -field Entry

Contains an array of structures of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpscsientry">HBAFCPScsiEntry</a> that describe an HBA's bindings between operating system and fibre channel protocol (FCP) identifiers. 


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a> WMI method reports mappings between the information that uniquely identifies a set of logical units for the operating system and the fibre channel protocol (FCP) identifiers for these logical units.

The WMI tool suite generates a declaration of the GetFcpTargetMapping_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfcptargetmapping">GetFcpTargetMapping</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpscsientry">HBAFCPScsiEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>
 

 

