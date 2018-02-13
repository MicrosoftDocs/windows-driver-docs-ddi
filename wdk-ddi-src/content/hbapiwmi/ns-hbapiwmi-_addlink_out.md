---
UID: NS:hbapiwmi._AddLink_OUT
title: "_AddLink_OUT"
author: windows-driver-content
description: The AddLink_OUT structure is used by an HBA miniport driver to report the status of a call to the AddLink WMI method.
old-location: storage\addlink_out.htm
old-project: storage
ms.assetid: fe088ec7-2577-488d-a1c7-a7e2a1f86f6a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbapiwmi/PAddLink_OUT, PAddLink_OUT structure pointer [Storage Devices], hbapiwmi/AddLink_OUT, storage.addlink_out, structs-Fibre_5f49a86f-a59f-4572-bfa2-5bb78dfe599b.xml, PAddLink_OUT, AddLink_OUT structure [Storage Devices], *PAddLink_OUT, AddLink_OUT, _AddLink_OUT
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
-	AddLink_OUT
product: Windows
targetos: Windows
req.typenames: "*PAddLink_OUT, AddLink_OUT"
---

# _AddLink_OUT structure


## -description


The AddLink_OUT structure is used by an HBA miniport driver to report the status of a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550128">AddLink</a> WMI method.


## -syntax


````
typedef struct _AddLink_OUT {
  ULONG HBAStatus;
} AddLink_OUT, *PAddLink_OUT;
````


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation.


## -remarks



The WMI tool suite generates a declaration of the AddLink_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550128">AddLink</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddLink_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

