---
UID: NF:wdm.IoWMISuggestInstanceName
title: IoWMISuggestInstanceName function (wdm.h)
description: The IoWMISuggestInstanceName routine is used to request that WMI suggest a base name which a driver can use to build WMI instance names for the device.
old-location: kernel\iowmisuggestinstancename.htm
tech.root: kernel
ms.assetid: a07ff2f6-e67e-489e-a477-6dc4b4ce6fed
ms.date: 04/30/2018
ms.keywords: IoWMISuggestInstanceName, IoWMISuggestInstanceName routine [Kernel-Mode Driver Architecture], k104_dc84cc9c-d6ca-40d2-93af-f54a149be7d1.xml, kernel.iowmisuggestinstancename, wdm/IoWMISuggestInstanceName
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoWMISuggestInstanceName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoWMISuggestInstanceName function


## -description


The <b>IoWMISuggestInstanceName</b> routine is used to request that WMI suggest a base name which a driver can use to build WMI instance names for the device.


## -parameters




### -param PhysicalDeviceObject [in, optional]

If supplied, points to the driver's physical device object.


### -param SymbolicLinkName [in, optional]

If supplied, points to the symbolic link name returned from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a>. 


### -param CombineNames [in]

If <b>TRUE</b> then the suggested names returned will combine the <i>PhysicalDeviceObject</i> and <i>SymbolicLinkName</i> information.


### -param SuggestedInstanceName [out]

A pointer to a buffer which upon successful completion will contain a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> which contains the suggested instance name. The caller is responsible for freeing this buffer when it is no longer needed.


## -returns



<b>IoWMISuggestInstanceName</b> returns a status code from the following list:

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
Indicates that WMI was able to successfully complete this function.

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
Indicates that insufficient resources were available to provide the caller with a buffer containing the Unicode string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
Indicates that insufficient resources were available to provide the caller with a buffer containing the Unicode string.

</td>
</tr>
</table>
 




## -remarks



If the <i>CombineNames</i> parameter is <b>TRUE</b> then both <i>PhysicalDeviceObject</i> and <i>SymbolicLinkName</i> must be specified. Otherwise, only one of them should be specified.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmiallocateinstanceids">IoWMIAllocateInstanceIds</a>
 

 

