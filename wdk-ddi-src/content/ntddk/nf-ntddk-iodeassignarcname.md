---
UID: NF:ntddk.IoDeassignArcName
title: IoDeassignArcName macro
author: windows-driver-content
description: The IoDeassignArcName routine removes a symbolic link between the ARC name for a device and the named device object.
old-location: kernel\iodeassignarcname.htm
old-project: kernel
ms.assetid: 978fbe0a-ac10-4c83-870d-35d98775c233
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoDeassignArcName, ntddk/IoDeassignArcName, IoDeassignArcName routine [Kernel-Mode Driver Architecture], kernel.iodeassignarcname, k104_859767ed-5969-41db-a454-b7808a1ef131.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoDeassignArcName
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoDeassignArcName macro


## -description


The <b>IoDeassignArcName</b> routine removes a symbolic link between the ARC name for a device and the named device object. 


## -syntax


````
VOID IoDeassignArcName(
  _In_ PUNICODE_STRING ArcName
);
````


## -parameters




### -param ArcName [in]

Pointer to a buffered Unicode string that is the ARC name. 


## -remarks



<b>IoDeassignArcName</b> is generally called if the driver is deleting the device object, for example, when the driver is unloading. 




## -see-also

<a href="..\ntddk\nf-ntddk-ioassignarcname.md">IoAssignArcName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoDeassignArcName routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

