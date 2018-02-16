---
UID: NS:storport.ST_PARAMETER_DATA
title: ST_PARAMETER_DATA
author: windows-driver-content
description: The ST_PARAMETER_DATA structure contains the parameter list for the set timestamp command.
old-location: storage\st_parameter_data.htm
old-project: storage
ms.assetid: C50F45EC-433C-421D-BD02-4C86CB44D5A4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PST_PARAMETER_DATA, ST_PARAMETER_DATA, scsi/ST_PARAMETER_DATA, PST_PARAMETER_DATA, ST_PARAMETER_DATA structure [Storage Devices], PST_PARAMETER_DATA structure pointer [Storage Devices], scsi/PST_PARAMETER_DATA, storage.st_parameter_data"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
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
-	scsi.h
apiname:
-	ST_PARAMETER_DATA
product: Windows
targetos: Windows
req.typenames: ST_PARAMETER_DATA, *PST_PARAMETER_DATA
req.product: Windows 10 or later.
---

# ST_PARAMETER_DATA structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>ST_PARAMETER_DATA</b> structure contains the parameter list for the set timestamp command. 


## -syntax


````
typedef struct _ST_PARAMETER_DATA {
  UCHAR Reserved1[4];
  UCHAR Timestamp[6];
  UCHAR Reserved2[2];
} ST_PARAMETER_DATA, *PST_PARAMETER_DATA;
````


## -struct-fields




### -field Reserved1

Reserved for future use.


### -field Timestamp

Specifies the value to which a device clock shall be initialized. The timestamp
should be the number of milliseconds that have elapsed since midnight, 1 January 1970 UT.


### -field Reserved2

Reserved for future use.


## -see-also

<a href="..\storport\ns-storport-rt_parameter_data.md">RT_PARAMETER_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ST_PARAMETER_DATA structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

