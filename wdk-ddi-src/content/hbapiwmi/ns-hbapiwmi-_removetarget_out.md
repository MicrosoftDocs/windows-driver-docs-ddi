---
UID: NS:hbapiwmi._RemoveTarget_OUT
title: "_RemoveTarget_OUT"
author: windows-driver-content
description: The RemoveTarget_OUT structure is used by an HBA miniport driver to report the output parameter data of the RemoveTarget WMI method to the WMI client.
old-location: storage\removetarget_out.htm
old-project: storage
ms.assetid: 176dbb0c-227e-48b2-956c-9e2b42f4c68b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PRemoveTarget_OUT, ,, O, P, PRemoveTarget_OUT, PRemoveTarget_OUT structure pointer [Storage Devices], R, RemoveTarget_OUT, RemoveTarget_OUT structure [Storage Devices], T, U, _, _RemoveTarget_OUT, a, e, g, hbapiwmi/PRemoveTarget_OUT, hbapiwmi/RemoveTarget_OUT, m, o, r, storage.removetarget_out, structs-Fibre_0cab8f87-0c96-4e03-bfd9-495e245850ca.xml, t, v"
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
-	RemoveTarget_OUT
product: Windows
targetos: Windows
req.typenames: RemoveTarget_OUT, *PRemoveTarget_OUT
---

# _RemoveTarget_OUT structure


## -description


The RemoveTarget_OUT structure is used by an HBA miniport driver to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564030">RemoveTarget</a> WMI method to the WMI client.


## -syntax


````
typedef struct _RemoveTarget_OUT {
  ULONG HBAStatus;
} RemoveTarget_OUT, *PRemoveTarget_OUT;
````


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


## -remarks



The WMI tool suite generates a declaration of the RemoveTarget_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564030">RemoveTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveTarget_OUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

