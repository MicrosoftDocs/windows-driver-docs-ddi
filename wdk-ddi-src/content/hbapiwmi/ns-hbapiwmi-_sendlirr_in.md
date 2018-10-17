---
UID: NS:hbapiwmi._SendLIRR_IN
title: "_SendLIRR_IN"
author: windows-driver-content
description: The SendLIRR_IN structure is used to deliver parameter data to the SendLIRR WMI method.
old-location: storage\sendlirr_in.htm
tech.root: storage
ms.assetid: 774acafb-c929-483a-82b0-2a358054dc7f
ms.date: 3/29/2018
ms.keywords: "*PSendLIRR_IN, PSendLIRR_IN, PSendLIRR_IN structure pointer [Storage Devices], SendLIRR_IN, SendLIRR_IN structure [Storage Devices], _SendLIRR_IN, hbapiwmi/PSendLIRR_IN, hbapiwmi/SendLIRR_IN, storage.sendlirr_in, structs-Fibre_6f0fd3c1-9eb5-4042-b12e-8dd225d966b1.xml"
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
-	SendLIRR_IN
product:
- Windows
targetos: Windows
req.typenames: SendLIRR_IN, *PSendLIRR_IN
---

# _SendLIRR_IN structure


## -description


The SendLIRR_IN structure is used to deliver parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565419">SendLIRR</a> WMI method. 


## -struct-fields




### -field SourceWWN

Contains a worldwide name for the local port through which the link incident record registration (LIRR) command is sent. 


### -field DestWWN

Contains a worldwide name for the destination port. 


### -field Function

Contains the code that identifies which registration function is to be performed. For an explanation of which values can be assigned to this member, see the T11 committee's <i>Fibre Channel Framing and Signaling</i> specification. 


### -field Type

Indicates the device type for which link information is requested. For an explanation of which values can be assigned to this member, see the T11 committee's <i>Fibre Channel Framing and Signaling</i> specification. 


## -remarks



The WMI tool suite generates a declaration of the SendLIRR_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565419">SendLIRR</a>
 

 

