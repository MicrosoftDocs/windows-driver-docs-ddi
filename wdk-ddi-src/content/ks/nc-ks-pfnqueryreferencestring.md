---
UID: NC:ks.PFNQUERYREFERENCESTRING
title: PFNQUERYREFERENCESTRING (ks.h)
description: This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using ExFreePool.
old-location: stream\kstrqueryreferencestring.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PFNQUERYREFERENCESTRING callback function"]
ms.keywords: KStrQueryReferenceString, KStrQueryReferenceString routine [Streaming Media Devices], PFNQUERYREFERENCESTRING, ks/KStrQueryReferenceString, ksfunc_ce750f42-efeb-4861-b451-ef0f8be40f9a.xml, stream.kstrqueryreferencestring
req.header: ks.h
req.include-header: Ks.h, Swenum.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFNQUERYREFERENCESTRING
 - ks/PFNQUERYREFERENCESTRING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNQUERYREFERENCESTRING
---

# PFNQUERYREFERENCESTRING callback function (ks.h)


## -description

This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>.

## -parameters

### -param Context 

[in]
Pointer to a device extension of the device's PDO.

### -param String 

[in, out]
Pointer to a string containing the reference string associated with the PDO.

## -returns

None.

## -remarks

The driver can access this method through the <b>QueryReferenceString</b> member of the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-bus_interface_reference">BUS_INTERFACE_REFERENCE</a> structure.

