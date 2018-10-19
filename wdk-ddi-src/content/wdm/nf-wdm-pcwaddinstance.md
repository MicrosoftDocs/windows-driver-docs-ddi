---
UID: NF:wdm.PcwAddInstance
title: PcwAddInstance function
author: windows-driver-content
description: The PcwAddInstance function adds the specified instance of the counter set to the consumer buffer.
old-location: devtest\pcwaddinstance.htm
tech.root: devtest
ms.assetid: 041761dd-ce52-4018-a226-c5181858326c
ms.date: 02/23/2018
ms.keywords: PcwAddInstance, PcwAddInstance function [Driver Development Tools], devtest.pcwaddinstance, km_pcw_1819c4ec-a951-4069-a8ff-24cf11f1b68c.xml, wdm/PcwAddInstance
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PcwAddInstance
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcwAddInstance function


## -description


The <b>PcwAddInstance</b> function adds the specified instance of the counter set to the consumer buffer. 


## -parameters




### -param Buffer [in]

A pointer to the consumer buffer to which the instance of the counter set will be added. Depending on the purpose of the buffer, the function either adds an instance or collects data. 


### -param Name [in]

A pointer to the Unicode string that contains the name of the instance of the counter set.


### -param Id [in]

A numeric value that specifies the <i>Id</i> (identifier) associated with the instance of the counter set.


### -param Count [in]

The number of data blocks associated with this instance.


### -param Data [in]

A pointer to an array of data blocks containing the counter values of this instance.


## -returns



<b>PcwAddInstance</b> returns one of the following values:

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
The instance was successfully added to the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
One of the provider data blocks is too small. For example, suppose that during the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550323">PcwRegister</a>, the provider specifies that counter <i>X</i> is at offset 100 of the first data block of size 4 bytes. If the call to <b>PcwAddInstance</b> specifies that the first data block is 50 bytes, this error status is returned.

</td>
</tr>
</table>
 




## -remarks



The <b>PcwAddInstance</b> function either adds an instance or collects data depending on the purpose of the buffer. The purpose of the buffer is defined by the type of callback. The <b>PcwAddInstance</b> function is called from a <a href="https://msdn.microsoft.com/5058fc17-1016-45bc-a6ea-5e2458824e7b">PcwCallback</a> routine when the reason is either to collect data or to enumerate instances. You can get the <i>Buffer</i> from the <i>Info</i> parameter for the <i>PcwCallback</i> routine




## -see-also




<a href="https://msdn.microsoft.com/5058fc17-1016-45bc-a6ea-5e2458824e7b">PcwCallback</a>
 

 

