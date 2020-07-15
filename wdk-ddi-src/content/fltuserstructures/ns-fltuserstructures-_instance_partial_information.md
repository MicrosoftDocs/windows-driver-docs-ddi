---
UID: NS:fltuserstructures._INSTANCE_PARTIAL_INFORMATION
title: _INSTANCE_PARTIAL_INFORMATION (fltuserstructures.h)
description: The INSTANCE_PARTIAL_INFORMATION structure contains partial information for a minifilter instance.
old-location: ifsk\instance_partial_information.htm
tech.root: ifsk
ms.assetid: cabcb39c-1f8d-41dc-a6ec-78f3fb3911cf
ms.date: 04/16/2018
keywords: ["_INSTANCE_PARTIAL_INFORMATION structure"]
ms.keywords: FltSystemStructures_10279757-e7e1-49a9-aa12-184a830e1db7.xml, INSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION structure [Installable File System Drivers], PINSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION structure pointer [Installable File System Drivers], _INSTANCE_PARTIAL_INFORMATION, fltuserstructures/INSTANCE_PARTIAL_INFORMATION, fltuserstructures/PINSTANCE_PARTIAL_INFORMATION, ifsk.instance_partial_information
f1_keywords:
 - "fltuserstructures/INSTANCE_PARTIAL_INFORMATION"
req.header: fltuserstructures.h
req.include-header: FltUser.h, Fltkernel.h
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
- fltuserstructures.h
api_name:
- INSTANCE_PARTIAL_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# _INSTANCE_PARTIAL_INFORMATION structure


## -description


The INSTANCE_PARTIAL_INFORMATION structure contains partial information for a minifilter instance. 


## -struct-fields




### -field NextEntryOffset

Byte offset of the next INSTANCE_PARTIAL_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one. 


### -field InstanceNameLength

Length, in bytes, of the instance name. 


### -field InstanceNameBufferOffset

Byte offset of the first character of the instance name string. This character is followed in memory by the remainder of the string. 


### -field AltitudeLength

Length, in bytes, of the altitude string for the instance. 


### -field AltitudeBufferOffset

Byte offset of the first character of the altitude string. This character is followed in memory by the remainder of the string. 


## -remarks



This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/fltuser/nf-fltuser-filterattachataltitude">FilterAttachAtAltitude</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterinstancefindclose">FilterInstanceFindClose</a>



<a href="https://docs.microsoft.com/windows/win32/api/fltuser/nf-fltuser-filterinstancefindfirst">FilterInstanceFindFirst</a>



<a href="https://docs.microsoft.com/windows/win32/api/fltuser/nf-fltuser-filterinstancefindnext">FilterInstanceFindNext</a>



<a href="https://docs.microsoft.com/windows/win32/api/fltuser/nf-fltuser-filterinstancegetinformation">FilterInstanceGetInformation</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtervolumeinstancefindclose">FilterVolumeInstanceFindClose</a>



<a href="https://docs.microsoft.com/windows/win32/api/fltuser/nf-fltuser-filtervolumeinstancefindfirst">FilterVolumeInstanceFindFirst</a>



<a href="https://docs.microsoft.com/windows/win32/api/fltuser/nf-fltuser-filtervolumeinstancefindnext">FilterVolumeInstanceFindNext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_aggregate_standard_information">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_basic_information">INSTANCE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_instance_full_information">INSTANCE_FULL_INFORMATION</a>
 

 

