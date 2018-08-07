---
UID: NF:netrequest.NetRequestGetAdapter
title: NetRequestGetAdapter function
author: windows-driver-content
description: The NetRequestGetAdapter method retrieves the NETADAPTER object associated with a NETREQUEST. This method is reserved for system use. Do not call this method from your code.
ms.assetid: cdbc6009-26b3-4174-ba3f-d0129c72f98b
ms.author: windowsdriverdev
ms.date: 03/12/2018
ms.topic: function
ms.keywords: NetRequestGetAdapter
req.header: netrequest.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NetRequestGetAdapter
product:
-	Windows
targetos: Windows

---

# NetRequestGetAdapter function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The NetRequestGetAdapter method retrieves the **NETADAPTER** object associated with a **NETREQUEST**. 

> [!WARNING]
> This method is reserved for system use. Do not call this method from your code.

## -parameters

### -param Request
The **NETREQUEST** object.

## -returns
Returns the **NETADAPTER** object associated with this **NETREQUEST**.

## -remarks
The minimum version for **NetRequestGetAdapter** is 1.2.

## -see-also