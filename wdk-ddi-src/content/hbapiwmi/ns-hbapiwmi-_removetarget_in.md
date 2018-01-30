---
UID: NS:hbapiwmi._RemoveTarget_IN
title: "_RemoveTarget_IN"
author: windows-driver-content
description: The RemoveTarget_IN structure is used by a WMI client to deliver input parameter data to the RemoveTarget WMI method.
old-location: storage\removetarget_in.htm
old-project: storage
ms.assetid: 54fcbb64-09ce-4f18-963b-fee2627d4231
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbapiwmi/PRemoveTarget_IN, storage.removetarget_in, PRemoveTarget_IN structure pointer [Storage Devices], hbapiwmi/RemoveTarget_IN, RemoveTarget_IN structure [Storage Devices], *PRemoveTarget_IN, PRemoveTarget_IN, _RemoveTarget_IN, RemoveTarget_IN, structs-Fibre_e284d48f-3a57-449f-8227-2e8637118dcd.xml
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
-	RemoveTarget_IN
product: Windows
targetos: Windows
req.typenames: "*PRemoveTarget_IN, RemoveTarget_IN"
---

# _RemoveTarget_IN structure


## -description


The RemoveTarget_IN structure is used by a WMI client to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564030">RemoveTarget</a> WMI method.


## -syntax


````
typedef struct _RemoveTarget_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DiscoveredPortWWN[8];
  ULONG AllTargets;
} RemoveTarget_IN, *PRemoveTarget_IN;
````


## -struct-fields




### -field HbaPortWWN

Contains a worldwide name that indicates the local port that should be removed from the list of ports whose events are reported to the WMI client.. 


### -field DiscoveredPortWWN

Contains a worldwide name that indicates the remote discovered port that should be removed from the list of ports whose events are reported to the WMI client.. 


### -field AllTargets

Indicates the scope of the target events to cease reporting. If this member is zero, the WMI provider client will cease reporting events associated with the port that is indicated by <b>DiscoveredPortWWN</b>. If this member is nonzero, the WMI provider will cease reporting all events associated any target. 


## -remarks


The WMI tool suite generates a declaration of the RemoveTarget_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564030">RemoveTarget</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveTarget_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

