---
UID: NE:netdispumdddi.MIRACAST_STATISTIC_TYPE
title: MIRACAST_STATISTIC_TYPE
author: windows-driver-content
description: Specifies types of Miracast statistics data that the user-mode display driver generates.
old-location: display\miracast_statistic_type.htm
old-project: display
ms.assetid: 1062e816-f10d-42eb-b0b5-4596b7b543f9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: MIRACAST_STATISTIC_TYPE, MIRACAST_STATISTIC_TYPE enumeration [Display Devices], MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE, MIRACAST_STATISTIC_TYPE_CHUNK_SENT, MIRACAST_STATISTIC_TYPE_EVENT, MIRACAST_STATISTIC_TYPE_FORCE_UINT32, display.miracast_statistic_type, netdispumdddi/MIRACAST_STATISTIC_TYPE, netdispumdddi/MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE, netdispumdddi/MIRACAST_STATISTIC_TYPE_CHUNK_SENT, netdispumdddi/MIRACAST_STATISTIC_TYPE_EVENT, netdispumdddi/MIRACAST_STATISTIC_TYPE_FORCE_UINT32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Netdispumdddi.h
api_name:
-	MIRACAST_STATISTIC_TYPE
product: Windows
targetos: Windows
req.typenames: MIRACAST_STATISTIC_TYPE
---

# MIRACAST_STATISTIC_TYPE enumeration


## -description


Specifies  types of Miracast statistics data that the user-mode display driver generates.


## -syntax


````
typedef enum  { 
  MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE  = 0,
  MIRACAST_STATISTIC_TYPE_CHUNK_SENT                 = 1,
  MIRACAST_STATISTIC_TYPE_EVENT                      = 2,
  MIRACAST_STATISTIC_TYPE_FORCE_UINT32               = 0xffffffff
} MIRACAST_STATISTIC_TYPE;
````


## -enum-fields




### -field MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE

The user-mode display driver has completed its processing of the encode chunk.


### -field MIRACAST_STATISTIC_TYPE_CHUNK_SENT

The driver has successfully sent the encode chunk to the network.


### -field MIRACAST_STATISTIC_TYPE_EVENT

Used by the user-mode display driver to report certain Miracast protocol events to the operating system for diagnostic purposes.


### -field MIRACAST_STATISTIC_TYPE_FORCE_UINT32

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.


## -remarks



For more info on how the driver uses these enumeration values with reporting calls to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_report_statistic.md">ReportStatistic</a> callback function, see <a href="https://msdn.microsoft.com/E1CE637F-42ED-4BEB-A2FF-04B4B88469DC">Reporting Miracast encode chunks and statistics</a>.




## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_report_statistic.md">ReportStatistic</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20MIRACAST_STATISTIC_TYPE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

