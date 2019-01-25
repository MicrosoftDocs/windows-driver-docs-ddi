---
UID: NF:ntddk.IoGetInitiatorProcess
title: IoGetInitiatorProcess function (ntddk.h)
description: The IoGetInitiatorProcess routine retrieves the process which initiated the creation of a file object if different than the process which is issuing the create.
old-location: kernel\iogetinitiatorprocess.htm
tech.root: kernel
ms.assetid: 653B4FD5-4C07-420A-BE8A-CC8C46BC6F0F
ms.date: 04/30/2018
ms.keywords: IoGetInitiatorProcess, IoGetInitiatorProcess function [Kernel-Mode Driver Architecture], kernel.iogetinitiatorprocess, ntddk/IoGetInitiatorProcess
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetInitiatorProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetInitiatorProcess function


## -description


The IoGetInitiatorProcess routine retrieves the process which initiated the creation of a file object if different than the process which is issuing the create.


## -parameters




### -param FileObject [in]

The file object from which to retrieve the initiator process.


## -returns



NULL if there is no initiator process. Otherwise, a pointer to which process initiated the creation of the file object.




## -remarks



A driver normally uses IoGetInitiatorProcess to determine which process has issued a request.  However, there are situations where a system component may issue a create on behalf of another process (after a successful create the component will duplicate the handle to the process).  This routine can be used if the driver must know which process the create operation is ultimately intended for. 



