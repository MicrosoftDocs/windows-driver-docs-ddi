---
UID: NS:hbapiwmi._GetBindingSupport_IN
title: "_GetBindingSupport_IN"
author: windows-driver-content
description: The GetBindingSupport_IN structure is used by a WMI client to deliver the input parameter data of the GetBindingSupport WMI method to the HBA miniport driver.
old-location: storage\getbindingsupport_in.htm
old-project: storage
ms.assetid: f5383092-9e77-4b58-911a-4842a3b9e9ef
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: GetBindingSupport_IN structure [Storage Devices], GetBindingSupport_IN, storage.getbindingsupport_in, PGetBindingSupport_IN, hbapiwmi/PGetBindingSupport_IN, hbapiwmi/GetBindingSupport_IN, PGetBindingSupport_IN structure pointer [Storage Devices], structs-Fibre_858abc05-6d3e-4630-a9f9-4b9aa742ea8e.xml, *PGetBindingSupport_IN, _GetBindingSupport_IN
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
-	GetBindingSupport_IN
product: Windows
targetos: Windows
req.typenames: "*PGetBindingSupport_IN, GetBindingSupport_IN"
---

# _GetBindingSupport_IN structure


## -description


The GetBindingSupport_IN structure is used by a WMI client to deliver the input parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553910">GetBindingSupport</a> WMI method to the HBA miniport driver.


## -syntax


````
typedef struct _GetBindingSupport_IN {
  UCHAR PortWWN[8];
} GetBindingSupport_IN, *PGetBindingSupport_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port whose persistent bindings are to be retrieved. 


## -remarks



The WMI tool suite generates a declaration of the GetBindingSupport_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553910">GetBindingSupport</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetBindingSupport_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

