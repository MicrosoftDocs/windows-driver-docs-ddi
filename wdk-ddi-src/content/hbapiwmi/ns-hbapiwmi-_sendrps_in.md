---
UID: NS:hbapiwmi._SendRPS_IN
title: "_SendRPS_IN"
author: windows-driver-content
description: The SendRPS_IN structure is used to deliver input parameter data to the SendRPS WMI method.
old-location: storage\sendrps_in.htm
old-project: storage
ms.assetid: 7ab8986d-1e28-4d25-888f-cd10e310d623
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSendRPS_IN, PSendRPS_IN, PSendRPS_IN structure pointer [Storage Devices], SendRPS_IN, SendRPS_IN structure [Storage Devices], _SendRPS_IN, hbapiwmi/PSendRPS_IN, hbapiwmi/SendRPS_IN, storage.sendrps_in, structs-Fibre_52ab21d3-f6bf-4e1d-b5a7-3f9cd054038c.xml"
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
-	SendRPS_IN
product: Windows
targetos: Windows
req.typenames: SendRPS_IN, *PSendRPS_IN
---

# _SendRPS_IN structure


## -description


The SendRPS_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565505">SendRPS</a> WMI method.


## -syntax


````
typedef struct _SendRPS_IN {
  UCHAR PortWWN[8];
  UCHAR AgentWWN[8];
  UCHAR ObjectWWN[8];
  ULONG AgentDomain;
  ULONG ObjectPortNumber;
} SendRPS_IN, *PSendRPS_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name for the local port through which the RPS command is sent. 


### -field AgentWWN

Contains a worldwide name for the port that is to be queried for the status of the port indicated by <b>ObjectWWN</b>. 


### -field ObjectWWN

Contains the worldwide name of the port for which port status is to be returned. 


### -field AgentDomain

Contains the domain number of the domain controller to be queried for the status of the port indicated by <b>ObjectWWN</b>. 


### -field ObjectPortNumber

Contains the worldwide name of the port for which port status is to be returned. 


## -remarks



The WMI tool suite generates a declaration of the SendRPS_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565505">SendRPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRPS_IN structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

