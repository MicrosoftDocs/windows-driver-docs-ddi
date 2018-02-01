---
UID: NF:ntddk.ExUuidCreate
title: ExUuidCreate function
author: windows-driver-content
description: The ExUuidCreate routine initializes a UUID (GUID) structure to a newly generated value.
old-location: kernel\exuuidcreate.htm
old-project: kernel
ms.assetid: e85fe5fa-b11e-41ff-a355-4da0394377d1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/ExUuidCreate, ExUuidCreate, kernel.exuuidcreate, ExUuidCreate routine [Kernel-Mode Driver Architecture], k102_e7d2044b-4f90-41bd-bac4-819c721e80c8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	ExUuidCreate
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# ExUuidCreate function


## -description


The <b>ExUuidCreate</b> routine initializes a UUID (GUID) structure to a newly generated value.


## -syntax


````
NTSTATUS ExUuidCreate(
  _Out_ UUID *Uuid
);
````


## -parameters




### -param Uuid [out]

A pointer to a caller-allocated UUID (GUID) structure that is set to a new UUID value. 


## -returns



            Possible return values include the following status codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_SUCCESS</b></b></dt>
</dl>
</td>
<td width="60%">
The routine successfully generated a UUID that is universally unique.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>RPC_NT_UUID_LOCAL_ONLY</b></b></dt>
</dl>
</td>
<td width="60%">
The routine generated a UUID that is unique only to this computer. This can occur when the MAC address is not an IEEE universally-administered address or when no NICs are present.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_RETRY</b></b></dt>
</dl>
</td>
<td width="60%">
The system is not ready to generate a new UUID.

</td>
</tr>
</table> 



## -remarks


A UUID and a GUID are the same data type.

The caller can iteratively attempt to obtain a new UUID value. 


