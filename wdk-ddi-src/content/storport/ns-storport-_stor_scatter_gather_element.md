---
UID: NS:storport._STOR_SCATTER_GATHER_ELEMENT
title: "_STOR_SCATTER_GATHER_ELEMENT"
author: windows-driver-content
description: The STOR_SCATTER_GATHER_ELEMENT structure is used with STOR_SCATTER_GATHER_LIST to build a list of scatter/gather elements.
old-location: storage\stor_scatter_gather_element.htm
old-project: storage
ms.assetid: 2e387418-a37c-492b-8ee4-b6ff8f0e53b0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSTOR_SCATTER_GATHER_ELEMENT, PSTOR_SCATTER_GATHER_ELEMENT, PSTOR_SCATTER_GATHER_ELEMENT structure pointer [Storage Devices], STOR_SCATTER_GATHER_ELEMENT, STOR_SCATTER_GATHER_ELEMENT structure [Storage Devices], _STOR_SCATTER_GATHER_ELEMENT, storage.stor_scatter_gather_element, storport/PSTOR_SCATTER_GATHER_ELEMENT, storport/STOR_SCATTER_GATHER_ELEMENT, structs-storport_e7e71caf-d421-45ba-b356-c1450eec6e6c.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
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
-	storport.h
api_name:
-	STOR_SCATTER_GATHER_ELEMENT
product: Windows
targetos: Windows
req.typenames: STOR_SCATTER_GATHER_ELEMENT, *PSTOR_SCATTER_GATHER_ELEMENT
req.product: Windows 10 or later.
---

# _STOR_SCATTER_GATHER_ELEMENT structure


## -description


The STOR_SCATTER_GATHER_ELEMENT structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567590">STOR_SCATTER_GATHER_LIST</a> to build a list of scatter/gather elements. 


## -struct-fields




### -field PhysicalAddress

Contains the physical address of the scatter/gather element. 


### -field Length

Contains the length in bytes of this scatter/gather element. 


### -field Reserved

Reserved. 


## -remarks



Miniport drivers used with the Storport driver retrieve an array of these structures using <a href="https://msdn.microsoft.com/library/windows/hardware/ff567097">StorPortGetScatterGatherList</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567590">STOR_SCATTER_GATHER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567097">StorPortGetScatterGatherList</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_SCATTER_GATHER_ELEMENT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

