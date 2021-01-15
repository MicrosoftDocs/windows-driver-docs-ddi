---
UID: NS:storport._STARTIO_PERFORMANCE_PARAMETERS
title: _STARTIO_PERFORMANCE_PARAMETERS (storport.h)
description: The STARTIO_PERFORMANCE_PARAMETERS structure describes the performance parameters that are returned to the miniport driver by the StorPortGetStartIoPerfParams routine.
old-location: storage\startio_performance_parameters.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STARTIO_PERFORMANCE_PARAMETERS structure"]
ms.keywords: "*PSTARTIO_PERFORMANCE_PARAMETERS, PSTARTIO_PERFORMANCE_PARAMETERS, PSTARTIO_PERFORMANCE_PARAMETERS structure pointer [Storage Devices], STARTIO_PERFORMANCE_PARAMETERS, STARTIO_PERFORMANCE_PARAMETERS structure [Storage Devices], _STARTIO_PERFORMANCE_PARAMETERS, storage.startio_performance_parameters, storport/PSTARTIO_PERFORMANCE_PARAMETERS, storport/STARTIO_PERFORMANCE_PARAMETERS, structs-storport_6f0f3ae8-51e3-4c3e-91e1-4603b04b6f08.xml"
req.header: storport.h
req.include-header: Storport.h
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
req.typenames: STARTIO_PERFORMANCE_PARAMETERS, *PSTARTIO_PERFORMANCE_PARAMETERS
f1_keywords:
 - _STARTIO_PERFORMANCE_PARAMETERS
 - storport/_STARTIO_PERFORMANCE_PARAMETERS
 - PSTARTIO_PERFORMANCE_PARAMETERS
 - storport/PSTARTIO_PERFORMANCE_PARAMETERS
 - STARTIO_PERFORMANCE_PARAMETERS
 - storport/STARTIO_PERFORMANCE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STARTIO_PERFORMANCE_PARAMETERS
 - PSTARTIO_PERFORMANCE_PARAMETERS
 - STARTIO_PERFORMANCE_PARAMETERS
---

# _STARTIO_PERFORMANCE_PARAMETERS structure


## -description

The <b>STARTIO_PERFORMANCE_PARAMETERS</b> structure describes the performance parameters that are returned to the miniport driver by the <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportgetstartioperfparams">StorPortGetStartIoPerfParams</a> routine.

## -struct-fields

### -field Version

The version number of the structure. This member is valid starting with Windows 8.

### -field Size

The size of the structure.

### -field MessageNumber

The offset in the device's MSI-X table for the optimal MSI-X message with which to interrupt. If the device does not support MSI-X messages, this member will be zero.

### -field ChannelNumber

Denotes the concurrent channel in which Storport is passing the I/O. If the miniport driver did not set up concurrent channels, this member will be zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportgetstartioperfparams">StorPortGetStartIoPerfParams</a>

