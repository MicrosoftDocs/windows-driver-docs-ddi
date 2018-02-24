---
UID: NS:hbapiwmi._SetPersistentEntry_IN
title: "_SetPersistentEntry_IN"
author: windows-driver-content
description: The SetPersistentEntry_IN structure is used by a WMI client to deliver the input parameter data of the SetPersistentEntry WMI method to the HBA miniport driver.
old-location: storage\setpersistententry_in.htm
old-project: storage
ms.assetid: f088a623-e6e8-4810-a7ab-90348f669dac
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-Fibre_7382da5e-059a-4e11-9db7-dbc3dae24928.xml, storage.setpersistententry_in, PSetPersistentEntry_IN structure pointer [Storage Devices], *PSetPersistentEntry_IN, hbapiwmi/SetPersistentEntry_IN, _SetPersistentEntry_IN, PSetPersistentEntry_IN, SetPersistentEntry_IN structure [Storage Devices], SetPersistentEntry_IN, hbapiwmi/PSetPersistentEntry_IN
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
-	SetPersistentEntry_IN
product: Windows
targetos: Windows
req.typenames: SetPersistentEntry_IN, *PSetPersistentEntry_IN
---

# _SetPersistentEntry_IN structure


## -description


The SetPersistentEntry_IN structure is used by a WMI client to deliver the input parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565783">SetPersistentEntry</a> WMI method to the HBA miniport driver.


## -syntax


````
typedef struct _SetPersistentEntry_IN {
  UCHAR               PortWWN[8];
  HBAFCPBindingEntry2 Binding;
} SetPersistentEntry_IN, *PSetPersistentEntry_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port whose persistent bindings will be changed. 


### -field Binding

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbafcpbindingentry2.md">HBAFCPBindingEntry2</a> that indicates the binding to be removed from the indicated port's list of bindings. 


## -remarks



The WMI tool suite generates a declaration of the SetPersistentEntry_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565783">SetPersistentEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetPersistentEntry_IN structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

