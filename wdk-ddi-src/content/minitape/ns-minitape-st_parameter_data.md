---
UID: NS:minitape.__unnamed_struct_14
title: ST_PARAMETER_DATA (minitape.h)
description: The ST_PARAMETER_DATA structure contains the parameter list for the set timestamp command.
old-location: storage\st_parameter_data.htm
tech.root: storage
ms.assetid: C50F45EC-433C-421D-BD02-4C86CB44D5A4
ms.date: 03/29/2018
keywords: ["ST_PARAMETER_DATA structure"]
ms.keywords: "*PST_PARAMETER_DATA, PST_PARAMETER_DATA, PST_PARAMETER_DATA structure pointer [Storage Devices], ST_PARAMETER_DATA, ST_PARAMETER_DATA structure [Storage Devices], scsi/PST_PARAMETER_DATA, scsi/ST_PARAMETER_DATA, storage.st_parameter_data"
req.header: minitape.h
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
targetos: Windows
req.typenames: ST_PARAMETER_DATA, *PST_PARAMETER_DATA
f1_keywords:
 - PST_PARAMETER_DATA
 - minitape/PST_PARAMETER_DATA
 - ST_PARAMETER_DATA
 - minitape/ST_PARAMETER_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - ST_PARAMETER_DATA
---

# ST_PARAMETER_DATA structure (minitape.h)


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>ST_PARAMETER_DATA</b> structure contains the parameter list for the set timestamp command.

## -struct-fields

### -field Reserved1

Reserved for future use.

### -field Timestamp

Specifies the value to which a device clock shall be initialized. The timestamp
should be the number of milliseconds that have elapsed since midnight, 1 January 1970 UT.

### -field Reserved2

Reserved for future use.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-rt_parameter_data">RT_PARAMETER_DATA</a>

