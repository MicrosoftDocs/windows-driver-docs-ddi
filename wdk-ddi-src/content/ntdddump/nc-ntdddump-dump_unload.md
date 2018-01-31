---
UID: NC:ntdddump.DUMP_UNLOAD
title: DUMP_UNLOAD
author: windows-driver-content
description: The Dump_Unload callback routine is called when the dump stack is unloaded.
old-location: storage\dump_unload.htm
old-project: storage
ms.assetid: 51a04ca9-4ccd-409e-b47a-1105637e6f6f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.dump_unload, Dump_Unload routine [Storage Devices], Dump_Unload, PDUMP_UNLOAD, PDUMP_UNLOAD, ntdddump/Dump_Unload, filter_rtns_01414353-4ca7-409e-a360-a7ad69a57b40.xml
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
-	Dump_Unload
product: Windows
targetos: Windows
req.typenames: VERIFY_INFORMATION, *PVERIFY_INFORMATION
---

# DUMP_UNLOAD callback


## -description


The <i>Dump_Unload</i> callback routine is called when the dump stack is unloaded. For the dump stack, this routine is called when the crash dump functionality is disabled. For the hibernation stack, this routine is called after the system resumes from hibernation. This gives the filter driver an opportunity to free any resources that it may have allocated or do any clean-up required by the filter driver.


## -prototype


````
PDUMP_UNLOAD Dump_Unload;

NTSTATUS Dump_Unload(
  _In_ PFILTER_EXTENSION FilterExtension
)
{ ... }
````


## -parameters




#### - FilterExtension [in]

A pointer to a <a href="..\ntdddump\ns-ntdddump-_filter_extension.md">FILTER_EXTENSION</a> structure.


## -returns


If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in <i>Ntstatus.h</i>.



## -see-also

<a href="..\ntdddump\ns-ntdddump-_filter_extension.md">FILTER_EXTENSION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20Dump_Unload routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

