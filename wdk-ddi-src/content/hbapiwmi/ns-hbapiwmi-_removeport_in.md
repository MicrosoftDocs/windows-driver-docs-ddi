---
UID: NS:hbapiwmi._RemovePort_IN
title: "_RemovePort_IN"
author: windows-driver-content
description: The Remove_IN structure is used by a WMI client to deliver input parameter data to the RemovePort WMI method.
old-location: storage\removeport_in.htm
old-project: storage
ms.assetid: 2f32e44a-e4a6-4745-9749-fc611119cc0e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PRemovePort_IN, PRemovePort_IN, PRemovePort_IN structure pointer [Storage Devices], RemovePort_IN, RemovePort_IN structure [Storage Devices], _RemovePort_IN, hbapiwmi/PRemovePort_IN, hbapiwmi/RemovePort_IN, storage.removeport_in, structs-Fibre_f60e236f-5ed1-4cc2-b685-6ee40895736e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	RemovePort_IN
product: Windows
targetos: Windows
req.typenames: RemovePort_IN, *PRemovePort_IN
---

# _RemovePort_IN structure


## -description


The Remove_IN structure is used by a WMI client to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564011">RemovePort</a> WMI method.


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port that should be removed from the list of ports whose events are reported to the WMI client.. 


## -remarks



The WMI tool suite generates a declaration of the RemovePort_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564011">RemovePort</a>
 

 

