---
UID: NS:hbapiwmi._GetFcpPersistentBinding_IN
title: _GetFcpPersistentBinding_IN
author: windows-driver-content
description: The GetFcpPersistentBinding_IN structure is used to pass input parameter data to the GetFcpPersistentBinding WMI method
old-location: storage\getfcppersistentbinding_in.htm
old-project: storage
ms.assetid: b08354c8-ef4e-4330-8a3b-dcfe3a722a5d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PGetFcpPersistentBinding_IN structure pointer [Storage Devices], GetFcpPersistentBinding_IN structure [Storage Devices], hbapiwmi/PGetFcpPersistentBinding_IN, GetFcpPersistentBinding_IN, structs-Fibre_34b0e554-331b-4f99-ae8e-5c2e9855b641.xml, hbapiwmi/GetFcpPersistentBinding_IN, storage.getfcppersistentbinding_in, _GetFcpPersistentBinding_IN, PGetFcpPersistentBinding_IN, *PGetFcpPersistentBinding_IN
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
-	GetFcpPersistentBinding_IN
product: Windows
targetos: Windows
req.typenames: GetFcpPersistentBinding_IN, *PGetFcpPersistentBinding_IN
---

# _GetFcpPersistentBinding_IN structure


## -description


The GetFcpPersistentBinding_IN structure is used to pass input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method 


## -syntax


````
typedef struct _GetFcpPersistentBinding_IN {
  ULONG InEntryCount;
} GetFcpPersistentBinding_IN, *PGetFcpPersistentBinding_IN;
````


## -struct-fields




### -field InEntryCount

Indicates the number of binding entries that will fit in the buffer that the WMI client provides when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a> WMI method.


## -remarks


The WMI tool suite generates a declaration of the GetFcpPersistentBinding_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553966">GetFcpPersistentBinding</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetFcpPersistentBinding_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

