---
UID: NS:gnssdriver.GNSS_BREADCRUMB_LIST
title: GNSS_BREADCRUMB_LIST
author: windows-driver-content
description: This structure contains the response to an IOCTL_GNSS_POP_BREADCRUMBS.
old-location: gnss\gnss_breadcrumb_list.htm
old-project: gnss
ms.assetid: 40C11C4B-2FFE-452F-AA08-2BCD4B6A4F7F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST structure [Sensor Devices], PGNSS_BREADCRUMB_LIST, PGNSS_BREADCRUMB_LIST structure pointer [Sensor Devices], gnss.gnss_breadcrumb_list, gnssdriver/GNSS_BREADCRUMB_LIST, gnssdriver/PGNSS_BREADCRUMB_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_BREADCRUMB_LIST
product:
- Windows
targetos: Windows
req.typenames: GNSS_BREADCRUMB_LIST, *PGNSS_BREADCRUMB_LIST
---

# GNSS_BREADCRUMB_LIST structure


## -description


This structure contains the response to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt767992">IOCTL_GNSS_POP_BREADCRUMBS</a>.


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

