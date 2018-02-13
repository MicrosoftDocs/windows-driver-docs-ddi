---
UID: NS:hbapiwmi._RemovePersistentEntry_IN
title: "_RemovePersistentEntry_IN"
author: windows-driver-content
description: The RemovePersistentEntry_IN structure is used by a WMI client to deliver input parameter data to the RemovePersistentEntry WMI method.
old-location: storage\removepersistententry_in.htm
old-project: storage
ms.assetid: 7019ee37-2080-4ba3-ba39-977e575ec04e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PRemovePersistentEntry_IN structure pointer [Storage Devices], PRemovePersistentEntry_IN, hbapiwmi/PRemovePersistentEntry_IN, structs-Fibre_e5e794c3-e43c-4218-af52-3f2d8a96c256.xml, _RemovePersistentEntry_IN, RemovePersistentEntry_IN, *PRemovePersistentEntry_IN, storage.removepersistententry_in, RemovePersistentEntry_IN structure [Storage Devices], hbapiwmi/RemovePersistentEntry_IN
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
-	RemovePersistentEntry_IN
product: Windows
targetos: Windows
req.typenames: "*PRemovePersistentEntry_IN, RemovePersistentEntry_IN"
---

# _RemovePersistentEntry_IN structure


## -description


The RemovePersistentEntry_IN structure is used by a WMI client to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563988">RemovePersistentEntry</a> WMI method.


## -syntax


````
typedef struct _RemovePersistentEntry_IN {
  UCHAR               PortWWN[8];
  HBAFCPBindingEntry2 Binding;
} RemovePersistentEntry_IN, *PRemovePersistentEntry_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port for which a persistent binding will be removed. 


### -field Binding

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry2.md">HBAFCPBindingEntry2</a> that indicates the binding to be removed from the indicated port's list of bindings. 


## -remarks



The WMI tool suite generates a declaration of the RemovePersistentEntry_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563988">RemovePersistentEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePersistentEntry_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

