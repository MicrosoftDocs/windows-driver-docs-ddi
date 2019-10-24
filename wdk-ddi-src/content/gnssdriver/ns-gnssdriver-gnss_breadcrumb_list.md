---
UID: NS:gnssdriver.__unnamed_struct_18
title: GNSS_BREADCRUMB_LIST (gnssdriver.h)
description: This structure contains the response to an IOCTL_GNSS_POP_BREADCRUMBS.
old-location: gnss\gnss_breadcrumb_list.htm
tech.root: gnss
ms.assetid: 40C11C4B-2FFE-452F-AA08-2BCD4B6A4F7F
ms.date: 02/15/2018
ms.keywords: "*PGNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST structure [Sensor Devices], PGNSS_BREADCRUMB_LIST, PGNSS_BREADCRUMB_LIST structure pointer [Sensor Devices], gnss.gnss_breadcrumb_list, gnssdriver/GNSS_BREADCRUMB_LIST, gnssdriver/PGNSS_BREADCRUMB_LIST"
ms.topic: struct
f1_keywords:
 - "gnssdriver/GNSS_BREADCRUMB_LIST"
req.header: gnssdriver.h
req.include-header: 
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
- gnssdriver.h
api_name:
- GNSS_BREADCRUMB_LIST
product:
- Windows
targetos: Windows
req.typenames: GNSS_BREADCRUMB_LIST, *PGNSS_BREADCRUMB_LIST
---

# GNSS_BREADCRUMB_LIST structure


## -description


This structure contains the response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ni-gnssdriver-ioctl_gnss_pop_breadcrumbs">IOCTL_GNSS_POP_BREADCRUMBS</a>.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field NumCrumbs

The number of breadcrumbs in the <b>IOCTL_GNSS_POP_BREADCRUMBS</b> response.


### -field v1

 




#### - v1[50]

An array of individual breadcrumbs returned in the in the <b>IOCTL_GNSS_POP_BREADCRUMBS</b> response.

