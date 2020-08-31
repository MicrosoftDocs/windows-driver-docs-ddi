---
UID: NS:hbapiwmi._GetDiscoveredPortAttributes_IN
title: _GetDiscoveredPortAttributes_IN (hbapiwmi.h)
description: The GetDiscoveredPortAttributes_IN structure is used to pass input parameter data to the GetDiscoveredPortAttributes WMI method.
old-location: storage\getdiscoveredportattributes_in.htm
tech.root: storage
ms.assetid: 99129f8e-c047-4e9f-bcaa-3cbcd2d30915
ms.date: 03/29/2018
keywords: ["GetDiscoveredPortAttributes_IN structure"]
ms.keywords: "*PGetDiscoveredPortAttributes_IN, GetDiscoveredPortAttributes_IN, GetDiscoveredPortAttributes_IN structure [Storage Devices], PGetDiscoveredPortAttributes_IN, PGetDiscoveredPortAttributes_IN structure pointer [Storage Devices], _GetDiscoveredPortAttributes_IN, hbapiwmi/GetDiscoveredPortAttributes_IN, hbapiwmi/PGetDiscoveredPortAttributes_IN, storage.getdiscoveredportattributes_in, structs-Fibre_5154a471-3acc-4eea-86c7-2292ccc230fb.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
req.typenames: GetDiscoveredPortAttributes_IN, *PGetDiscoveredPortAttributes_IN
f1_keywords:
 - _GetDiscoveredPortAttributes_IN
 - hbapiwmi/_GetDiscoveredPortAttributes_IN
 - PGetDiscoveredPortAttributes_IN
 - hbapiwmi/PGetDiscoveredPortAttributes_IN
 - GetDiscoveredPortAttributes_IN
 - hbapiwmi/GetDiscoveredPortAttributes_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - GetDiscoveredPortAttributes_IN
---

# _GetDiscoveredPortAttributes_IN structure


## -description

The GetDiscoveredPortAttributes_IN structure is used to pass input parameter data to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getdiscoveredportattributes">GetDiscoveredPortAttributes</a> WMI method.

## -struct-fields

### -field PortIndex

Indicates the index within the specified HBA of the port of type Nx_Port to query. For a definition of Nx_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA).

### -field DiscoveredPortIndex

Indicates the index within the specified HBA of the port of type FC_Port to query. For a definition of FC_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA).

## -remarks

The WMI tool suite generates a declaration of the GetDiscoveredPortAttributes_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getdiscoveredportattributes">GetDiscoveredPortAttributes</a>

