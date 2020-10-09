---
UID: NS:hbapiwmi._AddPort_IN
title: _AddPort_IN (hbapiwmi.h)
description: The AddPort_IN structure is used by a WMI client to deliver the input parameter data of the AddPort WMI method to the HBA miniport driver.
old-location: storage\addport_in.htm
tech.root: storage
ms.assetid: c9cdc0fc-e292-4142-a070-50a25a2a5673
ms.date: 03/29/2018
keywords: ["AddPort_IN structure"]
ms.keywords: "*PAddPort_IN, AddPort_IN, AddPort_IN structure [Storage Devices], PAddPort_IN, PAddPort_IN structure pointer [Storage Devices], _AddPort_IN, hbapiwmi/AddPort_IN, hbapiwmi/PAddPort_IN, storage.addport_in, structs-Fibre_0f7b349b-048b-444c-b8ac-bdf63b00f998.xml"
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
req.typenames: AddPort_IN, *PAddPort_IN
f1_keywords:
 - _AddPort_IN
 - hbapiwmi/_AddPort_IN
 - PAddPort_IN
 - hbapiwmi/PAddPort_IN
 - AddPort_IN
 - hbapiwmi/AddPort_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - AddPort_IN
---

# _AddPort_IN structure


## -description

The AddPort_IN structure is used by a WMI client to deliver the input parameter data of the <a href="/previous-versions/ff545022(v=vs.85)">AddPort</a> WMI method to the HBA miniport driver.

## -struct-fields

### -field PortWWN

Contains a worldwide name that indicates the port whose events are to be reported.

## -see-also

<a href="/previous-versions/ff545022(v=vs.85)">AddPort</a>