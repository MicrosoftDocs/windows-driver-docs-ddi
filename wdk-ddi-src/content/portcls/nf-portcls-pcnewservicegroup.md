---
UID: NF:portcls.PcNewServiceGroup
title: PcNewServiceGroup function (portcls.h)
description: The PcNewServiceGroup function creates and initializes a service group.
old-location: audio\pcnewservicegroup.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PcNewServiceGroup function"]
ms.keywords: PcNewServiceGroup, PcNewServiceGroup function [Audio Devices], audio.pcnewservicegroup, audpc-routines_2164b9cd-1bb5-4e51-aa07-6ed9cb40e3fb.xml, portcls/PcNewServiceGroup
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewServiceGroup function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PcNewServiceGroup
 - portcls/PcNewServiceGroup
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcNewServiceGroup
---

# PcNewServiceGroup function


## -description

The <b>PcNewServiceGroup</b> function creates and initializes a service group.

## -parameters

### -param OutServiceGroup 

[out]
Pointer to the service-group object created by this function. This parameter points to the caller-allocated pointer variable into which the function outputs the pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.

### -param OuterUnknown 

[in, optional]
Pointer to the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.

## -returns

<b>PcNewServiceGroup</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

The <i>OutServiceGroup</i> and <i>OuterUnknown</i> parameters follow the <a href="/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>
