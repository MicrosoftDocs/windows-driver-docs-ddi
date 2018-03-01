---
UID: NS:ntddk._WHEA_PERSISTENCE_INFO
title: "_WHEA_PERSISTENCE_INFO"
author: windows-driver-content
description: The WHEA_PERSISTENCE_INFO union describes data that is used by the error record persistence interface for storing an error record.
old-location: whea\whea_persistence_info.htm
old-project: whea
ms.assetid: ab429d1b-0b4d-4897-b5f0-73113d16758e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_PERSISTENCE_INFO, PWHEA_PERSISTENCE_INFO, PWHEA_PERSISTENCE_INFO union pointer [WHEA Drivers and Applications], WHEA_PERSISTENCE_INFO, WHEA_PERSISTENCE_INFO union [WHEA Drivers and Applications], _WHEA_PERSISTENCE_INFO, ntddk/PWHEA_PERSISTENCE_INFO, ntddk/WHEA_PERSISTENCE_INFO, whea.whea_persistence_info, whearef_0c5f7bbf-fc55-4667-b97a-9b28ec014bb5.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_PERSISTENCE_INFO
product: Windows
targetos: Windows
req.typenames: WHEA_PERSISTENCE_INFO, *PWHEA_PERSISTENCE_INFO
---

# _WHEA_PERSISTENCE_INFO structure


## -description


The WHEA_PERSISTENCE_INFO union describes data that is used by the error record persistence interface for storing an error record.


## -syntax


````
typedef union _WHEA_PERSISTENCE_INFO {
  struct {
    ULONGLONG Signature  :16;
    ULONGLONG Length  :24;
    ULONGLONG Identifier  :16;
    ULONGLONG Attributes  :2;
    ULONGLONG DoNotLog  :1;
    ULONGLONG Reserved  :5;
  };
  ULONGLONG AsULONGLONG;
} WHEA_PERSISTENCE_INFO, *PWHEA_PERSISTENCE_INFO;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field AsULONGLONG

A ULONGLONG representation of the contents of the WHEA_PERSISTENCE_INFO union.


#### - Signature

The signature of the error record when it is stored in the platform's persistent data storage. This member contains the value 'RE'.


#### - Length

The length, in bytes, of the error record when it is stored in the platform's persistent data storage.


#### - Identifier

An identifier that uniquely identifies the error record when it is stored in the platform's persistent data storage. The data type for this identifier is WHEA_ERROR_RECORD_ID.


#### - Attributes

Attribute flags that describe the error record. No attributes are currently defined.


#### - DoNotLog

A single bit that indicates that WHEA should not log an entry in the system event log for the error record.


#### - Reserved

Reserved for system use. This member must be zero.


## -remarks



A WHEA_PERSISTENCE_INFO union is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a> structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PERSISTENCE_INFO union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

