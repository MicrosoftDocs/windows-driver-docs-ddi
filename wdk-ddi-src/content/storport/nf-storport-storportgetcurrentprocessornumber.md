---
UID: NF:storport.StorPortGetCurrentProcessorNumber
title: StorPortGetCurrentProcessorNumber function (storport.h)
description: The StorPortGetCurrentProcessorNumber routine retrieves the current processor number from the kernel.
old-location: storage\storportgetcurrentprocessornumber.htm
tech.root: storage
ms.assetid: 10d77823-fcaa-43c3-b55e-74f2da97ecf0
ms.date: 03/29/2018
keywords: ["StorPortGetCurrentProcessorNumber function"]
ms.keywords: StorPortGetCurrentProcessorNumber, StorPortGetCurrentProcessorNumber routine [Storage Devices], storage.storportgetcurrentprocessornumber, storport/StorPortGetCurrentProcessorNumber, storprt_ac4d7e8b-eeb7-4b10-9c9e-cfe9acfddb24.xml
f1_keywords:
 - "storport/StorPortGetCurrentProcessorNumber"
 - "StorPortGetCurrentProcessorNumber"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortGetCurrentProcessorNumber
targetos: Windows
req.typenames: 
---

# StorPortGetCurrentProcessorNumber function


## -description


The <b>StorPortGetCurrentProcessorNumber</b> routine retrieves the current processor number from the kernel.


## -parameters




### -param HwDeviceExtension 
[in]
A pointer to the hardware device extension for the host bus adapter (HBA).


### -param ProcNumber 
[out]
A pointer to a processor number structure that holds the return data.


## -returns



The <b>StorPortGetCurrentProcessorNumber</b> routine returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>ProcNumber</i> is set to <b>NULL</b>.

</td>
</tr>
</table>
 



