---
UID: NS:hbapiwmi._RemovePort_IN
title: _RemovePort_IN (hbapiwmi.h)
description: The Remove_IN structure is used by a WMI client to deliver input parameter data to the RemovePort WMI method.
old-location: storage\removeport_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["RemovePort_IN structure"]
ms.keywords: "*PRemovePort_IN, PRemovePort_IN, PRemovePort_IN structure pointer [Storage Devices], RemovePort_IN, RemovePort_IN structure [Storage Devices], _RemovePort_IN, hbapiwmi/PRemovePort_IN, hbapiwmi/RemovePort_IN, storage.removeport_in, structs-Fibre_f60e236f-5ed1-4cc2-b685-6ee40895736e.xml"
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
req.typenames: RemovePort_IN, *PRemovePort_IN
f1_keywords:
 - _RemovePort_IN
 - hbapiwmi/_RemovePort_IN
 - PRemovePort_IN
 - hbapiwmi/PRemovePort_IN
 - RemovePort_IN
 - hbapiwmi/RemovePort_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _RemovePort_IN
 - PRemovePort_IN
 - RemovePort_IN
---

# _RemovePort_IN structure


## -description

The Remove_IN structure is used by a WMI client to deliver input parameter data to the <a href="/windows-hardware/drivers/storage/removeport">RemovePort</a> WMI method.

## -struct-fields

### -field PortWWN

Contains a worldwide name that indicates the port that should be removed from the list of ports whose events are reported to the WMI client..

## -remarks

The WMI tool suite generates a declaration of the RemovePort_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-eventcontrol-wmi-class">MSFC_EventControl WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/removeport">RemovePort</a>

