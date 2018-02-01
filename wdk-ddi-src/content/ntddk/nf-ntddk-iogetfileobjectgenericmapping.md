---
UID: NF:ntddk.IoGetFileObjectGenericMapping
title: IoGetFileObjectGenericMapping function
author: windows-driver-content
description: The IoGetFileObjectGenericMapping routine returns information about the mapping between each generic access right and the set of specific access rights for file objects.
old-location: kernel\iogetfileobjectgenericmapping.htm
old-project: kernel
ms.assetid: eae8a64f-c80a-4e70-b332-6cc098273d7c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_90acd8aa-7b11-4ee8-b6c7-84e7c849b131.xml, IoGetFileObjectGenericMapping routine [Kernel-Mode Driver Architecture], ntddk/IoGetFileObjectGenericMapping, kernel.iogetfileobjectgenericmapping, IoGetFileObjectGenericMapping
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetFileObjectGenericMapping
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetFileObjectGenericMapping function


## -description


The <b>IoGetFileObjectGenericMapping</b> routine returns information about the mapping between each generic access right and the set of specific access rights for file objects.


## -syntax


````
PGENERIC_MAPPING  IoGetFileObjectGenericMapping(void);
````


## -parameters





## -returns


<b>IoGetFileObjectGenericMapping</b> returns a pointer to the <a href="..\wdm\ns-wdm-_generic_mapping.md">GENERIC_MAPPING</a> structure that describes the mapping between each generic access right and the implied set of specific access rights.



## -see-also

<a href="..\wdm\nf-wdm-iocheckshareaccess.md">IoCheckShareAccess</a>

<a href="..\wdm\ns-wdm-_generic_mapping.md">GENERIC_MAPPING</a>

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>

<a href="..\wdm\nf-wdm-iosetshareaccess.md">IoSetShareAccess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetFileObjectGenericMapping routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

