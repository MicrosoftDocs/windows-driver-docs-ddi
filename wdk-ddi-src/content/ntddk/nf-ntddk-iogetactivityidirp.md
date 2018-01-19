---
UID: NF:ntddk.IoGetActivityIdIrp
title: IoGetActivityIdIrp function
author: windows-driver-content
description: The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP.
old-location: kernel\iogetactivityidirp.htm
old-project: kernel
ms.assetid: FAFF65EF-F1D8-4B54-B281-D5C4AC124E32
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetActivityIdIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetActivityIdIrp
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetActivityIdIrp function



## -description
The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP.



## -syntax

````
NTSTATUS IoGetActivityIdIrp(
  _In_  PIRP   Irp,
  _Out_ LPGUID Guid
);
````


## -parameters

### -param Irp [in]

The IRP from which to retrieve the activity ID.


### -param Guid [out]

A pointer to a location  to store the retrieved GUID.


## -returns
IoGetActivityIdIrp returns STATUS_SUCCESS if the call is successful. Possible error return values include the following.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>No activity ID is associated with the request.

 


## -remarks
