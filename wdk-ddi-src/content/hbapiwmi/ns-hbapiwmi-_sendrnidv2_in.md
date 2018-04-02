---
UID: NS:hbapiwmi._SendRNIDV2_IN
title: "_SendRNIDV2_IN"
author: windows-driver-content
description: The SendRNIDV2_IN structure is used to deliver input parameter data to the SendRNIDV2 WMI method.
old-location: storage\sendrnidv2_in.htm
old-project: storage
ms.assetid: b9c0833d-96ac-41cb-815f-b2df27f46cb4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSendRNIDV2_IN, PSendRNIDV2_IN, PSendRNIDV2_IN structure pointer [Storage Devices], SendRNIDV2_IN, SendRNIDV2_IN structure [Storage Devices], _SendRNIDV2_IN, hbapiwmi/PSendRNIDV2_IN, hbapiwmi/SendRNIDV2_IN, storage.sendrnidv2_in, structs-Fibre_5411860d-c8c8-4f4d-b4cc-751973c3d02e.xml"
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
-	SendRNIDV2_IN
product: Windows
targetos: Windows
req.typenames: SendRNIDV2_IN, *PSendRNIDV2_IN
---

# _SendRNIDV2_IN structure


## -description


The SendRNIDV2_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565463">SendRNIDV2</a> WMI method.


## -struct-fields




### -field PortWWN

Contains a worldwide name for the local port through which the version 2 request node identification data (RNIDV2) command is sent. 


### -field DestWWN

Contains a worldwide name for the destination port. 


### -field DestFCID

Contains an address identifier of the destination port. For a description of the values that this member can have, see the T11 committee's specification for <i>Fibre Channel HBA API</i>.


### -field NodeIdDataFormat

Indicates the node identification data format. For a description of the values that this member can have, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


## -remarks



The WMI tool suite generates a declaration of the SendRNIDV2_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565463">SendRNIDV2</a>
 

 

