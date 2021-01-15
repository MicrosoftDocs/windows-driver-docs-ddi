---
UID: NS:61883._AV_PCR
title: _AV_PCR (61883.h)
description: The AV_PCR structure specifies settings for an input or output plug.
old-location: ieee\av_pcr.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["AV_PCR structure"]
ms.keywords: "*PAV_PCR, 61883/AV_PCR, 61883/PAV_PCR, 61883_structures_d8602c71-aca5-427d-a8bf-d1da914ebacc.xml, AV_PCR, AV_PCR structure [Buses], IEEE.av_pcr, PAV_PCR, PAV_PCR structure pointer [Buses], _AV_PCR"
req.header: 61883.h
req.include-header: 61883.h
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
req.typenames: AV_PCR, *PAV_PCR
f1_keywords:
 - _AV_PCR
 - 61883/_AV_PCR
 - PAV_PCR
 - 61883/PAV_PCR
 - AV_PCR
 - 61883/AV_PCR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 61883.h
api_name:
 - _AV_PCR
 - PAV_PCR
 - AV_PCR
---

# _AV_PCR structure


## -description

The AV_PCR structure specifies settings for an input or output plug.

## -struct-fields

### -field oPCR

Contains an <a href="/windows-hardware/drivers/ddi/61883/ns-61883-_opcr">OPCR</a> structure that contains initialization values for an output plug.

### -field iPCR

Contains an <a href="/windows-hardware/drivers/ddi/61883/ns-61883-_ipcr">IPCR</a> structure that contains initialization values for an input plug.

### -field ulongData

Reserved for internal use.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536961">Av61883_CreatePlug</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536995">Av61883_SetPlug</a>

