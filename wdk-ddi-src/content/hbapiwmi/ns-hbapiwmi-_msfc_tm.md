---
UID: NS:hbapiwmi._MSFC_TM
title: "_MSFC_TM"
author: windows-driver-content
description: The MSFC_TM structure is used by WMI providers to timestamp events.
old-location: storage\msfc_tm.htm
old-project: storage
ms.assetid: 7e27f53f-350e-4315-9de6-60835bddcbfb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PMSFC_TM, MSFC_TM, MSFC_TM structure [Storage Devices], PMSFC_TM, PMSFC_TM structure pointer [Storage Devices], _MSFC_TM, hbapiwmi/MSFC_TM, hbapiwmi/PMSFC_TM, storage.msfc_tm, structs-Fibre_5cca5127-bbcc-4a2f-9ad2-2daeecac1448.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	MSFC_TM
product: Windows
targetos: Windows
req.typenames: MSFC_TM, *PMSFC_TM
---

# _MSFC_TM structure


## -description


The MSFC_TM structure is used by WMI providers to timestamp events. 


## -syntax


````
typedef struct _MSFC_TM {
  ULONG tm_sec;
  ULONG tm_min;
  ULONG tm_hour;
  ULONG tm_mday;
  ULONG tm_mon;
  ULONG tm_year;
  ULONG tm_wday;
  ULONG tm_yday;
  ULONG tm_isdst;
} MSFC_TM, *PMSFC_TM;
````


## -struct-fields




### -field tm_sec

Indicates the number of seconds past the minute. This member must have a value between 0 and 59. 


### -field tm_min

Indicates the number of minutes after the hour. This member must have a value between 0 and 59.


### -field tm_hour

Indicates the number of hours since midnight. This member must have a value between 0 and 23.


### -field tm_mday

Indicates the day of the month. This member must have a value between 1 and 31.


### -field tm_mon

Indicates the number of months since January. This member must have a value between 0 and 11.


### -field tm_year

Indicates the number of years since 1900. 


### -field tm_wday

Indicates the number of days since Sunday. This member must have a value between 0 and 6.


### -field tm_yday

Indicates the number of days since January 1. This member must have a value between 0 and 365.


### -field tm_isdst

Indicates when <b>TRUE</b> that the time stamp complies with daylight savings time. When <b>FALSE</b>, indicates that the timestamp does not comply with daylight savings time. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562965">MSFC_TM WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_TM structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

