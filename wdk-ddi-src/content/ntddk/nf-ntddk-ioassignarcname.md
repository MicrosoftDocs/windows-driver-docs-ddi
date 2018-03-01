---
UID: NF:ntddk.IoAssignArcName
title: IoAssignArcName macro
author: windows-driver-content
description: The IoAssignArcName routine creates a symbolic link between the ARC name of a physical device and the name of the corresponding device object when it has been created.
old-location: kernel\ioassignarcname.htm
old-project: kernel
ms.assetid: ef8a132a-f593-4a25-bb9e-b4ed57801db2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoAssignArcName, IoAssignArcName routine [Kernel-Mode Driver Architecture], k104_ceeba02c-47cf-4c25-a339-d55ee9ebc216.xml, kernel.ioassignarcname, ntddk/IoAssignArcName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
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
-	IoAssignArcName
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoAssignArcName macro


## -description


The <b>IoAssignArcName</b> routine creates a symbolic link between the ARC name of a physical device and the name of the corresponding device object when it has been created.


## -syntax


````
VOID IoAssignArcName(
  _In_ PUNICODE_STRING ArcName,
  _In_ PUNICODE_STRING DeviceName
);
````


## -parameters




### -param ArcName [in]

Pointer to a buffer containing the ARC name of the device. The ARC name must be a Unicode string.


### -param DeviceName [in]

Pointer to a buffer containing the name of the device object, representing the same device. The device object name must be a Unicode string. 


## -remarks



Drivers of hard disk devices need not call this routine. Drivers of other mass storage devices, including floppy, CD-ROM, and tape devices, should call <b>IoAssignArcName</b> during their initialization. 




## -see-also

<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAssignArcName routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

