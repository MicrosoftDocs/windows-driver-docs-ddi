---
UID: NS:hbapiwmi._SendRLS_IN
title: _SendRLS_IN (hbapiwmi.h)
description: The SendRLS_IN structure is used to deliver input parameter data to the SendRLS WMI method.
old-location: storage\sendrls_in.htm
tech.root: storage
ms.assetid: ba78482f-243a-4f60-907e-8d5c4a702ef2
ms.date: 03/29/2018
ms.keywords: "*PSendRLS_IN, PSendRLS_IN, PSendRLS_IN structure pointer [Storage Devices], SendRLS_IN, SendRLS_IN structure [Storage Devices], _SendRLS_IN, hbapiwmi/PSendRLS_IN, hbapiwmi/SendRLS_IN, storage.sendrls_in, structs-Fibre_c78b38af-b1e5-4f98-a57c-9c4c81b4a5f3.xml"
f1_keywords:
 - "hbapiwmi/SendRLS_IN"
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
- SendRLS_IN
product:
- Windows
targetos: Windows
req.typenames: SendRLS_IN, *PSendRLS_IN
---

# _SendRLS_IN structure


## -description


The SendRLS_IN structure is used to deliver input parameter data to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendrls">SendRLS</a> WMI method.


## -struct-fields




### -field PortWWN

Contains a worldwide name for the local port through which the read link error status block (RLS) command is sent. 


### -field DestWWN

Contains a worldwide name for the destination port. 


## -remarks



The WMI tool suite generates a declaration of the SendRLS_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendrls">SendRLS</a>
 

 

