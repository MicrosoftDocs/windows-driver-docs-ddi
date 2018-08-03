---
UID: NS:hbapiwmi._SetBindingSupport_IN
title: "_SetBindingSupport_IN"
author: windows-driver-content
description: The SetBindingSupport_IN structure is used to deliver input parameter data to the SetBindingSupport WMI method.
old-location: storage\setbindingsupport_in.htm
tech.root: storage
ms.assetid: bdcd6f76-9a45-4687-b3ab-ece3e9419c44
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSetBindingSupport_IN, PSetBindingSupport_IN, PSetBindingSupport_IN structure pointer [Storage Devices], SetBindingSupport_IN, SetBindingSupport_IN structure [Storage Devices], _SetBindingSupport_IN, hbapiwmi/PSetBindingSupport_IN, hbapiwmi/SetBindingSupport_IN, storage.setbindingsupport_in, structs-Fibre_2545c261-7902-4fb8-9943-21087c281089.xml"
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
-	SetBindingSupport_IN
product:
- Windows
targetos: Windows
req.typenames: SetBindingSupport_IN, *PSetBindingSupport_IN
---

# _SetBindingSupport_IN structure


## -description


The SetBindingSupport_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565565">SetBindingSupport</a> WMI method.


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port whose persistent bindings are to be retrieved. 


### -field BindType

Contains a bitmap that indicates the ability of an HBA and its miniport driver to provide a specific set of features related to persistent binding. For a list of values that this parameter can have, see the description of the HBA_BIND_TYPE WMI class qualifier.


## -remarks



The WMI tool suite generates a declaration of the SetBindingSupport_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565565">SetBindingSupport</a>
 

 

