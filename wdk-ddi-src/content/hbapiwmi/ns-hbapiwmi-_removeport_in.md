---
UID: NS:hbapiwmi._RemovePort_IN
title: "_RemovePort_IN"
author: windows-driver-content
description: The Remove_IN structure is used by a WMI client to deliver input parameter data to the RemovePort WMI method.
old-location: storage\removeport_in.htm
old-project: storage
ms.assetid: 2f32e44a-e4a6-4745-9749-fc611119cc0e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PRemovePort_IN, PRemovePort_IN, PRemovePort_IN structure pointer [Storage Devices], RemovePort_IN, RemovePort_IN structure [Storage Devices], _RemovePort_IN, hbapiwmi/PRemovePort_IN, hbapiwmi/RemovePort_IN, storage.removeport_in, structs-Fibre_f60e236f-5ed1-4cc2-b685-6ee40895736e.xml"
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
-	RemovePort_IN
product: Windows
targetos: Windows
req.typenames: RemovePort_IN, *PRemovePort_IN
---

# _RemovePort_IN structure


## -description


The Remove_IN structure is used by a WMI client to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564011">RemovePort</a> WMI method.


## -syntax


````
typedef struct _RemovePort_IN {
  UCHAR PortWWN[8];
} RemovePort_IN, *PRemovePort_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port that should be removed from the list of ports whose events are reported to the WMI client.. 


## -remarks



The WMI tool suite generates a declaration of the RemovePort_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564011">RemovePort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePort_IN structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

