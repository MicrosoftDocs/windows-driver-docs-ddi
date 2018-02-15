---
UID: NS:hbapiwmi._SetPersistentEntry_OUT
title: "_SetPersistentEntry_OUT"
author: windows-driver-content
description: The SetPersistentEntry_OUT structure is used to report the output parameter data of the SetPersistentEntry WMI method to the WMI client.
old-location: storage\setpersistententry_out.htm
old-project: storage
ms.assetid: c2089ae9-e872-4bbb-8e7b-fe11082d2b46
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSetPersistentEntry_OUT structure pointer [Storage Devices], SetPersistentEntry_OUT structure [Storage Devices], hbapiwmi/PSetPersistentEntry_OUT, *PSetPersistentEntry_OUT, storage.setpersistententry_out, _SetPersistentEntry_OUT, SetPersistentEntry_OUT, PSetPersistentEntry_OUT, structs-Fibre_3dbfc9dd-6c90-4908-bb5d-c331a2e0334c.xml, hbapiwmi/SetPersistentEntry_OUT
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
-	SetPersistentEntry_OUT
product: Windows
targetos: Windows
req.typenames: SetPersistentEntry_OUT, *PSetPersistentEntry_OUT
---

# _SetPersistentEntry_OUT structure


## -description


The SetPersistentEntry_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565783">SetPersistentEntry</a> WMI method to the WMI client.


## -syntax


````
typedef struct _SetPersistentEntry_OUT {
  ULONG HBAStatus;
} SetPersistentEntry_OUT, *PSetPersistentEntry_OUT;
````


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


## -remarks



The WMI tool suite generates a declaration of the SetPersistentEntry_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565783">SetPersistentEntry</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetPersistentEntry_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

