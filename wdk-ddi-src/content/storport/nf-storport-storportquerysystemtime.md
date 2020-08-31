---
UID: NF:storport.StorPortQuerySystemTime
title: StorPortQuerySystemTime function (storport.h)
description: The StoriPortQuerySystemTime routine obtains the current system time.
old-location: storage\storportquerysystemtime.htm
tech.root: storage
ms.assetid: 20677d16-136c-47d7-a19b-21731433298e
ms.date: 03/29/2018
keywords: ["StorPortQuerySystemTime function"]
ms.keywords: StorPortQuerySystemTime, StorPortQuerySystemTime routine [Storage Devices], storage.storportquerysystemtime, storport/StorPortQuerySystemTime, storprt_fcad0e23-f796-4cd9-935c-6db56a63d899.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortQuerySystemTime
 - storport/StorPortQuerySystemTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortQuerySystemTime
---

# StorPortQuerySystemTime function


## -description

The <b>StoriPortQuerySystemTime</b> routine obtains the current system time.

## -parameters

### -param CurrentTime 

[out]
Pointer to the current time, on return.

## -returns

None

## -remarks

The system time returned in <i>CurrentTime</i> is the number of 100-nanosecond intervals that have elapsed since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportquerysystemtime">ScsiPortQuerySystemTime</a>

