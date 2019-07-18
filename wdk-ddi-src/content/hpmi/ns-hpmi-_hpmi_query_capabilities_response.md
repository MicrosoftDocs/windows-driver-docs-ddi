---
UID: NS:hpmi._HPMI_QUERY_CAPABILITIES_RESPONSE
title: _HPMI_QUERY_CAPABILITIES_RESPONSE (hpmi.h)
description: HPMI_QUERY_CAPABILITIES_RESPONSE is a structure used to return information about software defined batteries (SDB).
old-location: powermeter\hpmi_query_capabilities_response.htm
tech.root: powermeter
ms.assetid: 2D7B6278-6D7A-41C4-B21A-D531CD8DCD91
ms.date: 05/08/2018
ms.keywords: "*PHPMI_QUERY_CAPABILITIES_RESPONSE, HPMI_QUERY_CAPABILITIES_RESPONSE, HPMI_QUERY_CAPABILITIES_RESPONSE structure [Power Metering and Budgeting Devices], PHPMI_QUERY_CAPABILITIES_RESPONSE, PHPMI_QUERY_CAPABILITIES_RESPONSE structure pointer [Power Metering and Budgeting Devices], _HPMI_QUERY_CAPABILITIES_RESPONSE, hpmi/HPMI_QUERY_CAPABILITIES_RESPONSE, hpmi/PHPMI_QUERY_CAPABILITIES_RESPONSE, powermeter.hpmi_query_capabilities_response"
ms.topic: struct
f1_keywords:
 - "hpmi/HPMI_QUERY_CAPABILITIES_RESPONSE"
req.header: hpmi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of the Windows operating systems.
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
- hpmi.h
api_name:
- HPMI_QUERY_CAPABILITIES_RESPONSE
product:
- Windows
targetos: Windows
req.typenames: HPMI_QUERY_CAPABILITIES_RESPONSE, *PHPMI_QUERY_CAPABILITIES_RESPONSE
---

# _HPMI_QUERY_CAPABILITIES_RESPONSE structure


## -description


HPMI_QUERY_CAPABILITIES_RESPONSE is a structure used to return information about software defined batteries (SDB).


## -struct-fields




### -field Version

Set to HPMI_QUERY_CAPABILITIES_VERSION_1.  


### -field RequestService

Requests one or more Windows services as defined by
    HPMI_REQUEST_SERVICE_XXX.


### -field SdbCapabilities

Specifies Software Defined Battery (SDB) features supported by the system.

 This field is set to combination of one or more HPMI_CAPABILITY_SDB_XXX
    values logically OR'd. It should be set to HPMI_CAPABILITY_NOT_SUPPORTED to
    indicate that SDB is not supported.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hpmi/ns-hpmi-_hpmi_query_capabilities">HPMI_QUERY_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hpmi/ni-hpmi-ioctl_hpmi_query_capabilities">IOCTL_HPMI_QUERY_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hpmi/index">hpmi.h</a>
 

 


