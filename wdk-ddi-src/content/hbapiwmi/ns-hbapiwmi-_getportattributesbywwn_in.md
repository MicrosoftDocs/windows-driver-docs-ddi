---
UID: NS:hbapiwmi._GetPortAttributesByWWN_IN
title: _GetPortAttributesByWWN_IN (hbapiwmi.h)
description: The GetPortAttributesByWWN_IN structure is used by a WMI client to deliver input parameter data to the GetPortAttributesByWWN WMI method.
old-location: storage\getportattributesbywwn_in.htm
tech.root: storage
ms.assetid: 2b189ece-6c49-42e2-8ef2-b3db516fc844
ms.date: 03/29/2018
keywords: ["_GetPortAttributesByWWN_IN structure"]
ms.keywords: "*PGetPortAttributesByWWN_IN, GetPortAttributesByWWN_IN, GetPortAttributesByWWN_IN structure [Storage Devices], PGetPortAttributesByWWN_IN, PGetPortAttributesByWWN_IN structure pointer [Storage Devices], _GetPortAttributesByWWN_IN, hbapiwmi/GetPortAttributesByWWN_IN, hbapiwmi/PGetPortAttributesByWWN_IN, storage.getportattributesbywwn_in, structs-Fibre_0093904b-888e-48de-ba79-5302d0ed6b75.xml"
f1_keywords:
 - "hbapiwmi/GetPortAttributesByWWN_IN"
 - "GetPortAttributesByWWN_IN"
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
- GetPortAttributesByWWN_IN
targetos: Windows
req.typenames: GetPortAttributesByWWN_IN, *PGetPortAttributesByWWN_IN
---

# _GetPortAttributesByWWN_IN structure


## -description


The GetPortAttributesByWWN_IN structure is used by a WMI client to deliver input parameter data to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getportattributesbywwn">GetPortAttributesByWWN</a> WMI method. 


## -struct-fields




### -field wwn

Contains a worldwide name that identifies a port of type FC_Port.


## -remarks



The WMI tool suite generates a declaration of the GetPortAttributesByWWN_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

For a definition of FC_Port and a discussion of worldwide names, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getportattributesbywwn">GetPortAttributesByWWN</a>
 

 

