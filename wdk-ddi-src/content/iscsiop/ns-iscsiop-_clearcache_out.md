---
UID: NS:iscsiop._ClearCache_OUT
title: "_ClearCache_OUT"
author: windows-driver-content
description: The ClearCache_OUT structure holds the output data for the ClearCache method.
old-location: storage\clearcache_out.htm
old-project: storage
ms.assetid: ab97d0b0-00fc-499c-9b1b-83731fe8e935
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-iSCSI_e96c134a-dfb1-474a-b730-1fb6e8d8f86f.xml, *PClearCache_OUT, storage.clearcache_out, PClearCache_OUT, PClearCache_OUT structure pointer [Storage Devices], _ClearCache_OUT, iscsiop/ClearCache_OUT, ClearCache_OUT structure [Storage Devices], ClearCache_OUT, iscsiop/PClearCache_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
apiname:
-	ClearCache_OUT
product: Windows
targetos: Windows
req.typenames: ClearCache_OUT, *PClearCache_OUT
---

# _ClearCache_OUT structure


## -description


The ClearCache_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552442">ClearCache</a> method.


## -syntax


````
typedef struct _ClearCache_OUT {
  ULONG Status;
} ClearCache_OUT, *PClearCache_OUT;
````


## -struct-fields




### -field Status

On output from <b>ClearCache</b>, the status of the <b>ClearCache</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



You must implement this method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552442">ClearCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563135">MSiSCSI_SecurityConfigOperations WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ClearCache_OUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

