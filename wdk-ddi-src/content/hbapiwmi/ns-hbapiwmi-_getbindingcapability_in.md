---
UID: NS:hbapiwmi._GetBindingCapability_IN
title: "_GetBindingCapability_IN"
description: The GetBindingCapability_IN structure is used by a WMI client to deliver the input parameter data of the GetBindingCapability WMI method to the HBA miniport driver.
old-location: storage\getbindingcapability_in.htm
tech.root: storage
ms.assetid: cd4046db-f9f5-4c9e-8886-29504c727f67
ms.date: 03/29/2018
ms.keywords: "*PGetBindingCapability_IN, GetBindingCapability_IN, GetBindingCapability_IN structure [Storage Devices], PGetBindingCapability_IN, PGetBindingCapability_IN structure pointer [Storage Devices], _GetBindingCapability_IN, hbapiwmi/GetBindingCapability_IN, hbapiwmi/PGetBindingCapability_IN, storage.getbindingcapability_in, structs-Fibre_11549945-ce24-45b2-b547-724bfa1b2380.xml"
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
-	GetBindingCapability_IN
product:
- Windows
targetos: Windows
req.typenames: GetBindingCapability_IN, *PGetBindingCapability_IN
---

# _GetBindingCapability_IN structure


## -description


The GetBindingCapability_IN structure is used by a WMI client to deliver the input parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553902">GetBindingCapability</a> WMI method to the HBA miniport driver.


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port whose persistent bindings are to be retrieved. 


## -remarks



The WMI tool suite generates a declaration of the GetBindingCapability_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553902">GetBindingCapability</a>
 

 

