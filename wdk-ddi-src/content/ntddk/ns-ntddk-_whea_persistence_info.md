---
UID: NS:ntddk._WHEA_PERSISTENCE_INFO
title: "_WHEA_PERSISTENCE_INFO"
author: windows-driver-content
description: The WHEA_PERSISTENCE_INFO union describes data that is used by the error record persistence interface for storing an error record.
old-location: whea\whea_persistence_info.htm
tech.root: whea
ms.assetid: ab429d1b-0b4d-4897-b5f0-73113d16758e
ms.date: 2/20/2018
ms.keywords: "*PWHEA_PERSISTENCE_INFO, PWHEA_PERSISTENCE_INFO, PWHEA_PERSISTENCE_INFO union pointer [WHEA Drivers and Applications], WHEA_PERSISTENCE_INFO, WHEA_PERSISTENCE_INFO union [WHEA Drivers and Applications], _WHEA_PERSISTENCE_INFO, ntddk/PWHEA_PERSISTENCE_INFO, ntddk/WHEA_PERSISTENCE_INFO, whea.whea_persistence_info, whearef_0c5f7bbf-fc55-4667-b97a-9b28ec014bb5.xml"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_PERSISTENCE_INFO
product:
- Windows
targetos: Windows
req.typenames: WHEA_PERSISTENCE_INFO, *PWHEA_PERSISTENCE_INFO
---

# _WHEA_PERSISTENCE_INFO structure


## -description


The WHEA_PERSISTENCE_INFO union describes data that is used by the error record persistence interface for storing an error record.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.Signature

The signature of the error record when it is stored in the platform's persistent data storage. This member contains the value 'RE'.


### -field DUMMYSTRUCTNAME.Length

The length, in bytes, of the error record when it is stored in the platform's persistent data storage.


### -field DUMMYSTRUCTNAME.Identifier

An identifier that uniquely identifies the error record when it is stored in the platform's persistent data storage. The data type for this identifier is WHEA_ERROR_RECORD_ID.


### -field DUMMYSTRUCTNAME.Attributes

Attribute flags that describe the error record. No attributes are currently defined.


### -field DUMMYSTRUCTNAME.DoNotLog

A single bit that indicates that WHEA should not log an entry in the system event log for the error record.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use. This member must be zero.


### -field AsULONGLONG

A ULONGLONG representation of the contents of the WHEA_PERSISTENCE_INFO union.


## -remarks



A WHEA_PERSISTENCE_INFO union is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560487">WHEA_ERROR_RECORD_HEADER</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560487">WHEA_ERROR_RECORD_HEADER</a>
 

 

