---
UID: NS:gnssdriver.GNSS_BREADCRUMB_LIST
title: GNSS_BREADCRUMB_LIST (gnssdriver.h)
description: The GNSS_BREADCRUMB_LIST structure contains an IOCTL_GNSS_POP_BREADCRUMBS response.
tech.root: gnss
ms.date: 06/17/2022
keywords: ["GNSS_BREADCRUMB_LIST structure"]
ms.keywords: "*PGNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST, GNSS_BREADCRUMB_LIST structure [Sensor Devices], PGNSS_BREADCRUMB_LIST, PGNSS_BREADCRUMB_LIST structure pointer [Sensor Devices], gnss.gnss_breadcrumb_list, gnssdriver/GNSS_BREADCRUMB_LIST, gnssdriver/PGNSS_BREADCRUMB_LIST"
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
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
targetos: Windows
req.typenames: GNSS_BREADCRUMB_LIST, *PGNSS_BREADCRUMB_LIST
f1_keywords:
 - PGNSS_BREADCRUMB_LIST
 - gnssdriver/PGNSS_BREADCRUMB_LIST
 - GNSS_BREADCRUMB_LIST
 - gnssdriver/GNSS_BREADCRUMB_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_BREADCRUMB_LIST
 - GNSS_BREADCRUMB_LIST
---

## -description

The GNSS_BREADCRUMB_LIST structure contains an [IOCTL_GNSS_POP_BREADCRUMBS](./ni-gnssdriver-ioctl_gnss_pop_breadcrumbs.md) response.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field NumCrumbs

The number of breadcrumbs in the **IOCTL_GNSS_POP_BREADCRUMBS** response.

### -field v1

An array of individual breadcrumbs returned in the in the **IOCTL_GNSS_POP_BREADCRUMBS** response.

