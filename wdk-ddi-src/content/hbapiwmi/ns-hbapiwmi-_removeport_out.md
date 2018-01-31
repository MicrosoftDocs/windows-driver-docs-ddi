---
UID: NS:hbapiwmi._RemovePort_OUT
title: "_RemovePort_OUT"
author: windows-driver-content
description: The RemovePort_OUT structure is used by an HBA miniport driver to the output parameter data of the RemovePort WMI method to the WMI client.
old-location: storage\removeport_out.htm
old-project: storage
ms.assetid: 89cb75e4-5e3b-4277-b173-abed00a7360b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PRemovePort_OUT, PRemovePort_OUT structure pointer [Storage Devices], hbapiwmi/PRemovePort_OUT, storage.removeport_out, structs-Fibre_dc8be161-745b-4919-9227-e333933482cf.xml, PRemovePort_OUT, hbapiwmi/RemovePort_OUT, _RemovePort_OUT, RemovePort_OUT, RemovePort_OUT structure [Storage Devices]"
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
-	RemovePort_OUT
product: Windows
targetos: Windows
req.typenames: "*PRemovePort_OUT, RemovePort_OUT"
---

# _RemovePort_OUT structure


## -description


The RemovePort_OUT structure is used by an HBA miniport driver to the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564011">RemovePort</a> WMI method to the WMI client.


## -syntax


````
typedef struct _RemovePort_OUT {
  ULONG HBAStatus;
} RemovePort_OUT, *PRemovePort_OUT;
````


## -struct-fields




#### - HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


## -remarks


The WMI tool suite generates a declaration of the RemovePort_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564011">RemovePort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePort_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

