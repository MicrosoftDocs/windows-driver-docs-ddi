---
UID: NE:netdispumdddi.__unnamed_enum_2
title: MIRACAST_STATISTIC_TYPE (netdispumdddi.h)
description: Specifies types of Miracast statistics data that the user-mode display driver generates.
old-location: display\miracast_statistic_type.htm
tech.root: display
ms.assetid: 1062e816-f10d-42eb-b0b5-4596b7b543f9
ms.date: 05/10/2018
ms.keywords: MIRACAST_STATISTIC_TYPE, MIRACAST_STATISTIC_TYPE enumeration [Display Devices], MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE, MIRACAST_STATISTIC_TYPE_CHUNK_SENT, MIRACAST_STATISTIC_TYPE_EVENT, MIRACAST_STATISTIC_TYPE_FORCE_UINT32, display.miracast_statistic_type, netdispumdddi/MIRACAST_STATISTIC_TYPE, netdispumdddi/MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE, netdispumdddi/MIRACAST_STATISTIC_TYPE_CHUNK_SENT, netdispumdddi/MIRACAST_STATISTIC_TYPE_EVENT, netdispumdddi/MIRACAST_STATISTIC_TYPE_FORCE_UINT32
f1_keywords:
 - "netdispumdddi/MIRACAST_STATISTIC_TYPE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Netdispumdddi.h
api_name:
- MIRACAST_STATISTIC_TYPE
product:
- Windows
targetos: Windows
req.typenames: MIRACAST_STATISTIC_TYPE
---

# MIRACAST_STATISTIC_TYPE enumeration


## -description


Specifies  types of Miracast statistics data that the user-mode display driver generates.


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



For more info on how the driver uses these enumeration values with reporting calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_report_statistic">ReportStatistic</a> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/reporting-miracast-encode-chunks-and-statistics">Reporting Miracast encode chunks and statistics</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_report_statistic">ReportStatistic</a>
 

 

