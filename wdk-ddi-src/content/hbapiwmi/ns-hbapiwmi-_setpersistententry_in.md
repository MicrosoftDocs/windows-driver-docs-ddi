---
UID: NS:hbapiwmi._SetPersistentEntry_IN
title: _SetPersistentEntry_IN (hbapiwmi.h)
description: The SetPersistentEntry_IN structure is used by a WMI client to deliver the input parameter data of the SetPersistentEntry WMI method to the HBA miniport driver.
old-location: storage\setpersistententry_in.htm
tech.root: storage
ms.assetid: f088a623-e6e8-4810-a7ab-90348f669dac
ms.date: 03/29/2018
ms.keywords: "*PSetPersistentEntry_IN, PSetPersistentEntry_IN, PSetPersistentEntry_IN structure pointer [Storage Devices], SetPersistentEntry_IN, SetPersistentEntry_IN structure [Storage Devices], _SetPersistentEntry_IN, hbapiwmi/PSetPersistentEntry_IN, hbapiwmi/SetPersistentEntry_IN, storage.setpersistententry_in, structs-Fibre_7382da5e-059a-4e11-9db7-dbc3dae24928.xml"
ms.topic: struct
f1_keywords:
 - "hbapiwmi/SetPersistentEntry_IN"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- SetPersistentEntry_IN
product:
- Windows
targetos: Windows
req.typenames: SetPersistentEntry_IN, *PSetPersistentEntry_IN
---

# _SetPersistentEntry_IN structure


## -description


The SetPersistentEntry_IN structure is used by a WMI client to deliver the input parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setpersistententry">SetPersistentEntry</a> WMI method to the HBA miniport driver.


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port whose persistent bindings will be changed. 


### -field Binding

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hbapiwmi/ns-hbapiwmi-_hbafcpbindingentry2">HBAFCPBindingEntry2</a> that indicates the binding to be removed from the indicated port's list of bindings. 


## -remarks



The WMI tool suite generates a declaration of the SetPersistentEntry_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setpersistententry">SetPersistentEntry</a>
 

 

