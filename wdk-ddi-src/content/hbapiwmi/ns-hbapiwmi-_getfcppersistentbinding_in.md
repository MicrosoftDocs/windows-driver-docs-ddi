---
UID: NS:hbapiwmi._GetFcpPersistentBinding_IN
title: "_GetFcpPersistentBinding_IN"
author: windows-driver-content
description: The GetFcpPersistentBinding_IN structure is used to pass input parameter data to the GetFcpPersistentBinding WMI method
old-location: storage\getfcppersistentbinding_in.htm
old-project: storage
ms.assetid: b08354c8-ef4e-4330-8a3b-dcfe3a722a5d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PGetFcpPersistentBinding_IN, GetFcpPersistentBinding_IN, GetFcpPersistentBinding_IN structure [Storage Devices], PGetFcpPersistentBinding_IN, PGetFcpPersistentBinding_IN structure pointer [Storage Devices], _GetFcpPersistentBinding_IN, hbapiwmi/GetFcpPersistentBinding_IN, hbapiwmi/PGetFcpPersistentBinding_IN, storage.getfcppersistentbinding_in, structs-Fibre_34b0e554-331b-4f99-ae8e-5c2e9855b641.xml"
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
-	GetFcpPersistentBinding_IN
product: Windows
targetos: Windows
req.typenames: GetFcpPersistentBinding_IN, *PGetFcpPersistentBinding_IN
---

# _GetFcpPersistentBinding_IN structure


## -description


The GetFcpPersistentBinding_IN structure is used to pass input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method 


## -syntax


````
typedef struct _GetFcpPersistentBinding_IN {
  ULONG InEntryCount;
} GetFcpPersistentBinding_IN, *PGetFcpPersistentBinding_IN;
````


## -struct-fields




### -field InEntryCount

Indicates the number of binding entries that will fit in the buffer that the WMI client provides when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method.


## -remarks



The WMI tool suite generates a declaration of the GetFcpPersistentBinding_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a>



 

 


