---
UID: NC:ntdddump.DUMP_FINISH
title: DUMP_FINISH
author: windows-driver-content
description: The Dump_Finish callback routine is called after writing all the dump data. The dump port driver generally flushes the cache to ensure the data is stored on the storage media before the system powers down.
old-location: storage\dump_finish.htm
old-project: storage
ms.assetid: 6e267810-a7ad-4407-8d01-4a2cad7a37bc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Dump_Finish, Dump_Finish routine [Storage Devices], PDUMP_FINISH, filter_rtns_7d5c92a4-19b6-4ef1-9b86-a9ec250106ef.xml, ntdddump/Dump_Finish, storage.dump_finish
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntdddump.h
api_name:
-	Dump_Finish
product: Windows
targetos: Windows
req.typenames: VERIFY_INFORMATION, *PVERIFY_INFORMATION
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



 

 


