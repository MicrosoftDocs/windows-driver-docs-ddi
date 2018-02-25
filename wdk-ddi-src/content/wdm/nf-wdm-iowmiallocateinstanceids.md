---
UID: NF:wdm.IoWMIAllocateInstanceIds
title: IoWMIAllocateInstanceIds function
author: windows-driver-content
description: The IoWMIAllocateInstanceIds routine allocates one or more instance IDs that are unique to the GUID.
old-location: kernel\iowmiallocateinstanceids.htm
old-project: kernel
ms.assetid: c382689e-907c-473c-9ab1-da963d7f3ba3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, I, IoWMIAllocateInstanceIds, IoWMIAllocateInstanceIds routine [Kernel-Mode Driver Architecture], M, W, a, c, d, e, k104_52b2c9a6-e9c2-4c9f-b6f1-43ec8c72056a.xml, kernel.iowmiallocateinstanceids, l, n, o, s, t, wdm/IoWMIAllocateInstanceIds"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
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
-	IoWMIAllocateInstanceIds
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWMIAllocateInstanceIds function


## -description


The <b>IoWMIAllocateInstanceIds</b> routine allocates one or more instance IDs that are unique to the GUID.


## -syntax


````
NTSTATUS IoWMIAllocateInstanceIds(
  _In_  GUID  *Guid,
  _In_  ULONG InstanceCount,
  _Out_ ULONG *FirstInstanceId
);
````


## -parameters




### -param Guid [in]

Pointer to the GUID for which to generate instance identifiers. 


### -param InstanceCount [in]

Specifies how many instance identifiers should be provided. 


### -param FirstInstanceId [out]

Pointer to the first instance identifier that the driver should use. 


## -returns



<b>IoWMIAllocateInstanceIds</b> returns a status code from the following list:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that WMI successfully provided unique instance identifiers for the GUID specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the WMI services are not available. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that insufficient resources were available to provide the caller with instance IDs.

</td>
</tr>
</table>
 




## -remarks



If greater than one instance was requested in <i>InstanceCount</i> and the routine completed successfully, <i>FirstInstanceId</i> points to the first instance that the caller should use. For each instance requested beyond one, the caller should increment the value returned in *<i>FirstInstanceId</i>. For example, if the caller requested six instances and one was returned as the value of <i>FirstInstanceId</i>, the caller should use the values 1-6 as his unique instance identifiers.




## -see-also

<a href="..\wdm\nf-wdm-iowmisuggestinstancename.md">IoWmiSuggestInstanceName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIAllocateInstanceIds routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

