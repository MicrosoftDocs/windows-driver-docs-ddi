---
UID: NF:netadapter.NetAdapterStop
title: NetAdapterStop function
author: windows-driver-content
description: The NetAdapterStop method stops a NETADAPTER object.
tech.root: netvista
ms.assetid: b566be39-c819-4d37-bf35-9b3d56e04818
ms.author: windowsdriverdev
ms.date: 03/05/2018
ms.topic: function
ms.keywords: NetAdapterStop
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
-	NetAdapterStop
product:
-	Windows
targetos: Windows

---

# NetAdapterStop function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetAdapterStop** method stops a NETADAPTER object.

## -parameters

### -param Adapter
The **NETADAPTER** object created by a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

## -returns
This method does not return a value.

## -remarks
If the **NETADAPTER** object is already stopped, this method does nothing.

The system will bugcheck if supplied an invalid handle, such as if the **NETADAPTER** object has not been initialized and created yet.



## -see-also

[NetAdapterCreate](nf-netadapter-netadaptercreate.md)

[NetAdapterStart](nf-netadapter-netadapterstart.md)
