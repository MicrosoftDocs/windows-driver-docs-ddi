---
UID: NC:ntdddump.DUMP_FINISH
title: DUMP_FINISH
author: windows-driver-content
description: The Dump_Finish callback routine is called after writing all the dump data. The dump port driver generally flushes the cache to ensure the data is stored on the storage media before the system powers down.
old-location: storage\dump_finish.htm
old-project: storage
ms.assetid: 6e267810-a7ad-4407-8d01-4a2cad7a37bc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.dump_finish, Dump_Finish routine [Storage Devices], Dump_Finish, PDUMP_FINISH, PDUMP_FINISH, ntdddump/Dump_Finish, filter_rtns_7d5c92a4-19b6-4ef1-9b86-a9ec250106ef.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista and Windows Server 2008.
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
-	UserDefined
apilocation:
-	ntdddump.h
apiname:
-	Dump_Finish
product: Windows
targetos: Windows
req.typenames: "*PVERIFY_INFORMATION, VERIFY_INFORMATION"
---

# DUMP_FINISH callback


## -description


The <i>Dump_Finish</i> callback routine is called after writing all the dump data. The dump port driver generally flushes the cache to ensure the data is stored on the storage media before the system powers down.


## -prototype


````
PDUMP_FINISH Dump_Finish;

NTSTATUS Dump_Finish(
  _In_ PFILTER_EXTENSION FilterExtension
)
{ ... }
````


## -parameters




### -param FilterExtension [in]

A pointer to a <a href="..\ntdddump\ns-ntdddump-_filter_extension.md">FILTER_EXTENSION</a> structure.


## -returns



If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in <i>Ntstatus.h</i>.




## -see-also

<a href="..\ntdddump\ns-ntdddump-_filter_extension.md">FILTER_EXTENSION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20Dump_Finish routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

