---
UID: NS:hbapiwmi._SetBindingSupport_OUT
title: "_SetBindingSupport_OUT"
author: windows-driver-content
description: The SetBindingSupport_OUT structure is used to report the output parameter data of the SetBindingSupport WMI method to the WMI client.
old-location: storage\setbindingsupport_out.htm
old-project: storage
ms.assetid: f2b37780-0b33-4af9-9634-571b49be5791
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.setbindingsupport_out, PSetBindingSupport_OUT structure pointer [Storage Devices], hbapiwmi/PSetBindingSupport_OUT, structs-Fibre_95e0c3db-69d5-406f-98ea-6554eed922ef.xml, hbapiwmi/SetBindingSupport_OUT, *PSetBindingSupport_OUT, _SetBindingSupport_OUT, SetBindingSupport_OUT structure [Storage Devices], SetBindingSupport_OUT, PSetBindingSupport_OUT
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
-	SetBindingSupport_OUT
product: Windows
targetos: Windows
req.typenames: SetBindingSupport_OUT, *PSetBindingSupport_OUT
---

# _SetBindingSupport_OUT structure


## -description


The SetBindingSupport_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565565">SetBindingSupport</a> WMI method to the WMI client.


## -syntax


````
typedef struct _SetBindingSupport_OUT {
  ULONG HBAStatus;
} SetBindingSupport_OUT, *PSetBindingSupport_OUT;
````


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


## -remarks



The WMI tool suite generates a declaration of the SetBindingSupport_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565565">SetBindingSupport</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetBindingSupport_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

