---
UID: NS:hbapiwmi._GetPersistentBinding2_IN
title: "_GetPersistentBinding2_IN"
author: windows-driver-content
description: The GetPersistentBinding2_IN structure is used to deliver input parameter data to the GetPersistentBinding2 WMI method.
old-location: storage\getpersistentbinding2_in.htm
old-project: storage
ms.assetid: 646378f8-9037-4c40-bcbc-5ffe380e6279
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PGetPersistentBinding2_IN, GetPersistentBinding2_IN, GetPersistentBinding2_IN structure [Storage Devices], PGetPersistentBinding2_IN, PGetPersistentBinding2_IN structure pointer [Storage Devices], _GetPersistentBinding2_IN, hbapiwmi/GetPersistentBinding2_IN, hbapiwmi/PGetPersistentBinding2_IN, storage.getpersistentbinding2_in, structs-Fibre_3be7645f-006d-4a32-9739-d97e632edf58.xml"
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
-	GetPersistentBinding2_IN
product: Windows
targetos: Windows
req.typenames: GetPersistentBinding2_IN, *PGetPersistentBinding2_IN
---

# _GetPersistentBinding2_IN structure


## -description


The GetPersistentBinding2_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554959">GetPersistentBinding2</a> WMI method.


## -syntax


````
typedef struct _GetPersistentBinding2_IN {
  UCHAR PortWWN[8];
  ULONG InEntryCount;
} GetPersistentBinding2_IN, *PGetPersistentBinding2_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port whose persistent bindings are to be retrieved. 


### -field InEntryCount

Indicates the number of binding entries that the WMI provider can report.


## -remarks



The WMI tool suite generates a declaration of the GetPersistentBinding2_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554959">GetPersistentBinding2</a>



 

 


