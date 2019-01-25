---
UID: NS:hbapiwmi._GetPortAttributesByWWN_OUT
title: "_GetPortAttributesByWWN_OUT" (hbapiwmi.h)
description: The GetPortAttributesByWWN_OUT structure is used to report the output parameter data of the GetPortAttributesByWWN WMI method to the WMI client.
old-location: storage\getportattributesbywwn_out.htm
tech.root: storage
ms.assetid: 9a4d04de-2c44-4f13-ac6f-32e2fe879e4e
ms.date: 03/29/2018
ms.keywords: "*PGetPortAttributesByWWN_OUT, GetPortAttributesByWWN_OUT, GetPortAttributesByWWN_OUT structure [Storage Devices], PGetPortAttributesByWWN_OUT, PGetPortAttributesByWWN_OUT structure pointer [Storage Devices], _GetPortAttributesByWWN_OUT, hbapiwmi/GetPortAttributesByWWN_OUT, hbapiwmi/PGetPortAttributesByWWN_OUT, storage.getportattributesbywwn_out, structs-Fibre_bf13c322-2b55-4113-8e04-5cacfecbea8e.xml"
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
-	GetPortAttributesByWWN_OUT
product:
- Windows
targetos: Windows
req.typenames: GetPortAttributesByWWN_OUT, *PGetPortAttributesByWWN_OUT
---

# _GetPortAttributesByWWN_OUT structure


## -description


The GetPortAttributesByWWN_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554965">GetPortAttributesByWWN</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation.


### -field PortAttributes

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff562510">MSFC_HBAPortAttributesResults</a> that holds the port attributes to be reported.


## -remarks



The WMI tool suite generates a declaration of the GetPortAttributesByWWN_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554965">GetPortAttributesByWWN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562510">MSFC_HBAPortAttributesResults</a>
 

 

