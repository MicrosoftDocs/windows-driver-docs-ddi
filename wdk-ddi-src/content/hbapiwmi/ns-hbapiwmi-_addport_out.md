---
UID: NS:hbapiwmi._AddPort_OUT
title: _AddPort_OUT (hbapiwmi.h)
description: The AddPort_OUT structure is used by a WMI provider to report the output parameter data of the AddPort WMI method to the WMI client.
old-location: storage\addport_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AddPort_OUT structure"]
ms.keywords: "*PAddPort_OUT, AddPort_OUT, AddPort_OUT structure [Storage Devices], PAddPort_OUT, PAddPort_OUT structure pointer [Storage Devices], _AddPort_OUT, hbapiwmi/AddPort_OUT, hbapiwmi/PAddPort_OUT, storage.addport_out, structs-Fibre_2a5eecfb-36b6-4358-98d0-0c119b7697f0.xml"
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
req.typenames: AddPort_OUT, *PAddPort_OUT
f1_keywords:
 - _AddPort_OUT
 - hbapiwmi/_AddPort_OUT
 - PAddPort_OUT
 - hbapiwmi/PAddPort_OUT
 - AddPort_OUT
 - hbapiwmi/AddPort_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - AddPort_OUT
---

# _AddPort_OUT structure


## -description

The AddPort_OUT structure is used by a WMI provider to report the output parameter data of the <a href="/previous-versions/ff545022(v=vs.85)">AddPort</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -see-also

<a href="/previous-versions/ff545022(v=vs.85)">AddPort</a>
