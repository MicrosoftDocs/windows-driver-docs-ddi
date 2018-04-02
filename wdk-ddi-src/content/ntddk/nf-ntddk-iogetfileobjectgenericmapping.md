---
UID: NF:ntddk.IoGetFileObjectGenericMapping
title: IoGetFileObjectGenericMapping function
author: windows-driver-content
description: The IoGetFileObjectGenericMapping routine returns information about the mapping between each generic access right and the set of specific access rights for file objects.
old-location: kernel\iogetfileobjectgenericmapping.htm
old-project: kernel
ms.assetid: eae8a64f-c80a-4e70-b332-6cc098273d7c
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoGetFileObjectGenericMapping, IoGetFileObjectGenericMapping routine [Kernel-Mode Driver Architecture], k104_90acd8aa-7b11-4ee8-b6c7-84e7c849b131.xml, kernel.iogetfileobjectgenericmapping, ntddk/IoGetFileObjectGenericMapping
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetFileObjectGenericMapping
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetFileObjectGenericMapping function


## -description


The <b>IoGetFileObjectGenericMapping</b> routine returns information about the mapping between each generic access right and the set of specific access rights for file objects.


## -parameters






## -returns



<b>IoGetFileObjectGenericMapping</b> returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a> structure that describes the mapping between each generic access right and the implied set of specific access rights.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548341">IoCheckShareAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550324">IoSetShareAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>
 

 

