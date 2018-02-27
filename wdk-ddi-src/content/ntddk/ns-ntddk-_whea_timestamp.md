---
UID: NS:ntddk._WHEA_TIMESTAMP
title: "_WHEA_TIMESTAMP"
author: windows-driver-content
description: The WHEA_TIMESTAMP union describes the time that an error was reported to the operating system.
old-location: whea\whea_timestamp.htm
old-project: whea
ms.assetid: 70a6555d-1da9-4013-911a-4a9d011b0205
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_TIMESTAMP, PWHEA_TIMESTAMP, PWHEA_TIMESTAMP union pointer [WHEA Drivers and Applications], WHEA_TIMESTAMP, WHEA_TIMESTAMP union [WHEA Drivers and Applications], _WHEA_TIMESTAMP, ntddk/PWHEA_TIMESTAMP, ntddk/WHEA_TIMESTAMP, whea.whea_timestamp, whearef_d0fafe3b-0cea-4adf-a68a-b565e04ae258.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_TIMESTAMP
product: Windows
targetos: Windows
req.typenames: WHEA_TIMESTAMP, *PWHEA_TIMESTAMP
---

# _WHEA_TIMESTAMP structure


## -description


The WHEA_TIMESTAMP union describes the time that an error was reported to the operating system.


## -syntax


````
typedef union _WHEA_TIMESTAMP {
  struct {
    ULONGLONG Seconds  :8;
    ULONGLONG Minutes  :8;
    ULONGLONG Hours  :8;
    ULONGLONG Precise  :1;
    ULONGLONG Reserved  :7;
    ULONGLONG Day  :8;
    ULONGLONG Month  :8;
    ULONGLONG Year  :8;
    ULONGLONG Century  :8;
  };
  LARGE_INTEGER AsLARGE_INTEGER;
} WHEA_TIMESTAMP, *PWHEA_TIMESTAMP;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field AsLARGE_INTEGER

A LARGE_INTEGER representation of the contents of the WHEA_TIMESTAMP union.


#### - Century

The century.


#### - Day

The day of the month.


#### - Hours

The hour in the day.


#### - Minutes

The number of minutes past the hour.


#### - Month

The month of the year.


#### - Precise

If this member is set to 1, the timestamp correlates precisely to the time of the error event.

<div class="alert"><b>Note</b>  This member is supported in Windows 7 and later versions of Windows.</div>
<div> </div>

#### - Reserved

Reserved for system use.


#### - Seconds

The number of seconds past the minute.


#### - Year

The year within the century.


## -remarks



A WHEA_TIMESTAMP union is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a> structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_TIMESTAMP union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

