---
UID: NS:hbapiwmi._GetDiscoveredPortAttributes_OUT
title: _GetDiscoveredPortAttributes_OUT (hbapiwmi.h)
description: The GetDiscoveredPortAttributes_OUT structure is used to report the output parameter data of the GetDiscoveredPortAttributes WMI method to the WMI client.
old-location: storage\getdiscoveredportattributes_out.htm
tech.root: storage
ms.assetid: 7a6ae185-2f91-4285-b540-61130aef464c
ms.date: 03/29/2018
keywords: ["GetDiscoveredPortAttributes_OUT structure"]
ms.keywords: "*PGetDiscoveredPortAttributes_OUT, GetDiscoveredPortAttributes_OUT, GetDiscoveredPortAttributes_OUT structure [Storage Devices], PGetDiscoveredPortAttributes_OUT, PGetDiscoveredPortAttributes_OUT structure pointer [Storage Devices], _GetDiscoveredPortAttributes_OUT, hbapiwmi/GetDiscoveredPortAttributes_OUT, hbapiwmi/PGetDiscoveredPortAttributes_OUT, storage.getdiscoveredportattributes_out, structs-Fibre_611d9a0e-b0dc-472e-9bec-3902412e8ec4.xml"
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
req.typenames: GetDiscoveredPortAttributes_OUT, *PGetDiscoveredPortAttributes_OUT
f1_keywords:
 - _GetDiscoveredPortAttributes_OUT
 - hbapiwmi/_GetDiscoveredPortAttributes_OUT
 - PGetDiscoveredPortAttributes_OUT
 - hbapiwmi/PGetDiscoveredPortAttributes_OUT
 - GetDiscoveredPortAttributes_OUT
 - hbapiwmi/GetDiscoveredPortAttributes_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - GetDiscoveredPortAttributes_OUT
---

# _GetDiscoveredPortAttributes_OUT structure


## -description

The GetDiscoveredPortAttributes_OUT structure is used to report the output parameter data of the <a href="/windows-hardware/drivers/storage/getdiscoveredportattributes">GetDiscoveredPortAttributes</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a> that indicates the result of an HBA query operation.

### -field PortAttributes

Contains a structure of type <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_msfc_hbaportattributesresults">MSFC_HBAPortAttributesResults</a> that holds the port attributes to report.

## -remarks

The WMI tool suite generates a declaration of the GetDiscoveredPortAttributes_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/getdiscoveredportattributes">GetDiscoveredPortAttributes</a>