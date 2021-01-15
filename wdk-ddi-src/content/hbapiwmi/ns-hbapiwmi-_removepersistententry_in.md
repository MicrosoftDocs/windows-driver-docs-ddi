---
UID: NS:hbapiwmi._RemovePersistentEntry_IN
title: _RemovePersistentEntry_IN (hbapiwmi.h)
description: The RemovePersistentEntry_IN structure is used by a WMI client to deliver input parameter data to the RemovePersistentEntry WMI method.
old-location: storage\removepersistententry_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["RemovePersistentEntry_IN structure"]
ms.keywords: "*PRemovePersistentEntry_IN, PRemovePersistentEntry_IN, PRemovePersistentEntry_IN structure pointer [Storage Devices], RemovePersistentEntry_IN, RemovePersistentEntry_IN structure [Storage Devices], _RemovePersistentEntry_IN, hbapiwmi/PRemovePersistentEntry_IN, hbapiwmi/RemovePersistentEntry_IN, storage.removepersistententry_in, structs-Fibre_e5e794c3-e43c-4218-af52-3f2d8a96c256.xml"
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
req.typenames: RemovePersistentEntry_IN, *PRemovePersistentEntry_IN
f1_keywords:
 - _RemovePersistentEntry_IN
 - hbapiwmi/_RemovePersistentEntry_IN
 - PRemovePersistentEntry_IN
 - hbapiwmi/PRemovePersistentEntry_IN
 - RemovePersistentEntry_IN
 - hbapiwmi/RemovePersistentEntry_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _RemovePersistentEntry_IN
 - PRemovePersistentEntry_IN
 - RemovePersistentEntry_IN
---

# _RemovePersistentEntry_IN structure


## -description

The RemovePersistentEntry_IN structure is used by a WMI client to deliver input parameter data to the <a href="/windows-hardware/drivers/storage/removepersistententry">RemovePersistentEntry</a> WMI method.

## -struct-fields

### -field PortWWN

Contains a worldwide name that indicates the port for which a persistent binding will be removed.

### -field Binding

Contains a structure of type <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpbindingentry2">HBAFCPBindingEntry2</a> that indicates the binding to be removed from the indicated port's list of bindings.

## -remarks

The WMI tool suite generates a declaration of the RemovePersistentEntry_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/removepersistententry">RemovePersistentEntry</a>

