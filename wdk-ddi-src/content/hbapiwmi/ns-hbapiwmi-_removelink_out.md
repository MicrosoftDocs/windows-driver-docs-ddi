---
UID: NS:hbapiwmi._RemoveLink_OUT
title: "_RemoveLink_OUT"
author: windows-driver-content
description: The RemoveLink_OUT structure is used by an HBA miniport driver to report the output parameter data of the RemoveLink WMI method to the WMI client.
old-location: storage\removelink_out.htm
old-project: storage
ms.assetid: 724e3143-4994-4785-9bbf-afb928e8b166
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PRemoveLink_OUT, ,, L, O, P, PRemoveLink_OUT, PRemoveLink_OUT structure pointer [Storage Devices], R, RemoveLink_OUT, RemoveLink_OUT structure [Storage Devices], T, U, _, _RemoveLink_OUT, e, hbapiwmi/PRemoveLink_OUT, hbapiwmi/RemoveLink_OUT, i, k, m, n, o, storage.removelink_out, structs-Fibre_0210455d-c6c4-4548-ae14-63aa2e7b9a5d.xml, v"
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
-	RemoveLink_OUT
product: Windows
targetos: Windows
req.typenames: RemoveLink_OUT, *PRemoveLink_OUT
---

# _RemoveLink_OUT structure


## -description


The RemoveLink_OUT structure is used by an HBA miniport driver to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563984">RemoveLink</a> WMI method to the WMI client. 


## -syntax


````
typedef struct _RemoveLink_OUT {
  ULONG HBAStatus;
} RemoveLink_OUT, *PRemoveLink_OUT;
````


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


## -remarks



The WMI tool suite generates a declaration of the RemoveLink_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563984">RemoveLink</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveLink_OUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

