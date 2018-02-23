---
UID: NF:storport.StorPortGetLogicalProcessorRelationship
title: StorPortGetLogicalProcessorRelationship function
author: windows-driver-content
description: The StorPortGetLogicalProcessorRelationship routine returns relationship information for one or more specified types.
old-location: storage\storportgetlogicalprocessorrelationship.htm
old-project: storage
ms.assetid: 32b92771-7f23-492c-a3b0-b10032c9f80a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storprt_65b00469-41a4-446b-aaa5-fee877aaff3c.xml, StorPortGetLogicalProcessorRelationship, storage.storportgetlogicalprocessorrelationship, StorPortGetLogicalProcessorRelationship routine [Storage Devices], storport/StorPortGetLogicalProcessorRelationship
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortGetLogicalProcessorRelationship
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetLogicalProcessorRelationship function


## -description


The <b>StorPortGetLogicalProcessorRelationship</b> routine returns relationship information for one or more specified types. These types include groups, physical packages, and nodes in the host system. The information that is returned includes processor affinity masks that are composed of the logical processors in the host system. These logical processors share the specified relationship types.


## -syntax


````
ULONG StorPortGetLogicalProcessorRelationship(
  _In_     PVOID                                    HwDeviceExtension,
  _In_opt_ PPROCESSOR_NUMBER                        ProcessorNumber,
  _In_     LOGICAL_PROCESSOR_RELATIONSHIP           RelationshipType,
  _Out_    PSYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Information,
  _Inout_  PULONG                                   Length
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param ProcessorNumber [in, optional]

An optional pointer to a processor number for which relationships are to be returned. If this parameter is not provided, information about all processors is returned.


### -param RelationshipType [in]

The type of relationship to be returned.


### -param Information [out]

A pointer to a buffer that receives the specified information.


### -param Length [in, out]

A pointer to the length of the information buffer, in bytes. Upon return, this value receives the number of bytes that are populated with relationship information.


## -returns



The <b>StorPortGetLogicalProcessorRelationship</b>routine returns one of the following status codes:

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
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>Information</i> is set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The operation fails with this return value if one or more of the parameters are invalid, for example, if the supplied buffer is not large enough to hold the requested information.

</td>
</tr>
</table>
 



