---
UID: NS:hbapiwmi._SendRLS_IN
title: "_SendRLS_IN"
author: windows-driver-content
description: The SendRLS_IN structure is used to deliver input parameter data to the SendRLS WMI method.
old-location: storage\sendrls_in.htm
old-project: storage
ms.assetid: ba78482f-243a-4f60-907e-8d5c4a702ef2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-Fibre_c78b38af-b1e5-4f98-a57c-9c4c81b4a5f3.xml, *PSendRLS_IN, SendRLS_IN, SendRLS_IN structure [Storage Devices], PSendRLS_IN structure pointer [Storage Devices], PSendRLS_IN, _SendRLS_IN, hbapiwmi/SendRLS_IN, storage.sendrls_in, hbapiwmi/PSendRLS_IN
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	SendRLS_IN
product: Windows
targetos: Windows
req.typenames: SendRLS_IN, *PSendRLS_IN
---

# _SendRLS_IN structure


## -description


The SendRLS_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565442">SendRLS</a> WMI method.


## -syntax


````
typedef struct _SendRLS_IN {
  UCHAR PortWWN[8];
  UCHAR DestWWN[8];
} SendRLS_IN, *PSendRLS_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name for the local port through which the read link error status block (RLS) command is sent. 


### -field DestWWN

Contains a worldwide name for the destination port. 


## -remarks



The WMI tool suite generates a declaration of the SendRLS_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565442">SendRLS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRLS_IN structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

