---
UID: NS:storport.RT_PARAMETER_DATA
title: RT_PARAMETER_DATA (storport.h)
description: The RT_PARAMETER_DATA structure (storport.h) contains the parameter data for the report timestamp command.
old-location: storage\rt_parameter_data.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["RT_PARAMETER_DATA structure"]
ms.keywords: "*PRT_PARAMETER_DATA, PRT_PARAMETER_DATA, PRT_PARAMETER_DATA structure pointer [Storage Devices], RT_PARAMETER_DATA, RT_PARAMETER_DATA structure [Storage Devices], scsi/PRT_PARAMETER_DATA, scsi/RT_PARAMETER_DATA, storage.rt_parameter_data"
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
targetos: Windows
req.typenames: RT_PARAMETER_DATA, *PRT_PARAMETER_DATA
f1_keywords:
 - PRT_PARAMETER_DATA
 - storport/PRT_PARAMETER_DATA
 - RT_PARAMETER_DATA
 - storport/RT_PARAMETER_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - PRT_PARAMETER_DATA
 - RT_PARAMETER_DATA
---

# RT_PARAMETER_DATA structure (storport.h)


## -description

The **RT_PARAMETER_DATA** structure contains the parameter data for the report timestamp command.

## -struct-fields

### -field ParameterDataLength

Indicates the number of bytes that follow in the parameter data.

### -field Origin

Indicates the most recent event that initialized the returned device clock.

| Value | Meaning |
| ----- | ------- |
| 0     | Device clock initialized to zero at power on or as the result of a hard reset. |
| 1     | Reserved for future use. |
| 2     | Device clock initialized by the SET TIMESTAMP command. |
| 3     | Device clock initialized by an unknown method. |
| 4 to 7| Reserved for future use. |

### -field Reserved1

Reserved for future use.

### -field Reserved2

Reserved for future use.

### -field Timestamp

Contains the current value of a device clock.

### -field Reserved3

Reserved for future use.

## -see-also

[**ST_PARAMETER_DATA**](ns-storport-st_parameter_data.md)

