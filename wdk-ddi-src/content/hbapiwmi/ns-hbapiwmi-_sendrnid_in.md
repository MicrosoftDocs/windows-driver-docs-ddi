---
UID: NS:hbapiwmi._SendRNID_IN
title: "_SendRNID_IN"
author: windows-driver-content
description: The SendRNID_IN structure is used to deliver input parameter data to the SendRNID WMI method.
old-location: storage\sendrnid_in.htm
old-project: storage
ms.assetid: 668c4d1a-52e8-49ea-bd19-e789dfa8dfa5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSendRNID_IN, PSendRNID_IN, PSendRNID_IN structure pointer [Storage Devices], SendRNID_IN, SendRNID_IN structure [Storage Devices], _SendRNID_IN, hbapiwmi/PSendRNID_IN, hbapiwmi/SendRNID_IN, storage.sendrnid_in, structs-Fibre_506226e9-45f1-40d3-bd41-7b30fe16673e.xml"
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
-	SendRNID_IN
product: Windows
targetos: Windows
req.typenames: SendRNID_IN, *PSendRNID_IN
---

# _SendRNID_IN structure


## -description


The SendRNID_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565459">SendRNID</a> WMI method.


## -struct-fields




### -field wwn

Contains a worldwide name for the port to which the request node identification data (RNID) command is sent. 


### -field wwntype

Deprecated. Do not use. 


## -remarks



The WMI tool suite generates a declaration of the SendRNID_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565459">SendRNID</a>
 

 

