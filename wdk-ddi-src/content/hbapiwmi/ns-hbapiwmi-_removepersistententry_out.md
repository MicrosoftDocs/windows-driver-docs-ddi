---
UID: NS:hbapiwmi._RemovePersistentEntry_OUT
title: _RemovePersistentEntry_OUT
author: windows-driver-content
description: The RemovePersistentEntry_OUT structure is used to report the output parameter data of the RemovePersistentEntry WMI method to the WMI client.
old-location: storage\removepersistententry_out.htm
old-project: storage
ms.assetid: 2fa578f7-5892-4ec1-a01f-49c828bd6913
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _RemovePersistentEntry_OUT, RemovePersistentEntry_OUT, *PRemovePersistentEntry_OUT
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
req.alt-api: RemovePersistentEntry_OUT
req.alt-loc: hbapiwmi.h
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
req.typenames: RemovePersistentEntry_OUT, *PRemovePersistentEntry_OUT
---

# _RemovePersistentEntry_OUT structure



## -description
The RemovePersistentEntry_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563988">RemovePersistentEntry</a> WMI method to the WMI client.



## -syntax

````
typedef struct _RemovePersistentEntry_OUT {
  ULONG HBAStatus;
} RemovePersistentEntry_OUT, *PRemovePersistentEntry_OUT;
````


## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


## -remarks
The WMI tool suite generates a declaration of the RemovePersistentEntry_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563988">RemovePersistentEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePersistentEntry_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

